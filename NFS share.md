## STEP 1 — Install NFS Packages

dnf install -y nfs-utils

---

## ✅ STEP 2 — Enable & Start NFS Service

systemctl enable --now nfs-server

Verify:

systemctl status nfs-server

It should be **active (running)**.

3.159-> 10.124.3.151-3.158


## STEP 3 — Configure Export

Edit:

vi /etc/exports

Add this line:

/ekyc_bucket  192.168.1.0/24(rw,sync,no_root_squash)

🔹 Replace `192.168.1.0/24` with your client network  
OR allow specific server:

/ekyc_bucket  192.168.1.50(rw,sync,no_root_squash)

### Option meanings:

- `rw` → read/write access
    
- `sync` → safer write behavior
    
- `no_root_squash` → remote root keeps root privileges
    

If security matters, we can harden later.

---

## ✅ STEP 4 — Export the Share

exportfs -rav

Verify:

exportfs -v

---

## ✅ STEP 5 — Open Firewall

Check firewall:

systemctl status firewalld

If running:

firewall-cmd --permanent --add-service=nfs  
firewall-cmd --permanent --add-service=mountd  
firewall-cmd --permanent --add-service=rpc-bind  
firewall-cmd --reload

---

## ✅ STEP 6 — SELinux (Very Important in RHEL)

Check SELinux:

getenforce

If **Enforcing**, run:

setsebool -P nfs_export_all_rw 1

And set context:

chcon -Rt public_content_rw_t /ekyc_bucket

Or permanent method:

semanage fcontext -a -t public_content_rw_t "/ekyc_bucket(/.*)?"  
restorecon -Rv /ekyc_bucket

If `semanage` not found:

dnf install policycoreutils-python-utils



