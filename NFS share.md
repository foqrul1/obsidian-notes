## STEP 1 — Install NFS Packages

dnf install -y nfs-utils

---

## ✅ STEP 2 — Enable & Start NFS Service

systemctl enable --now nfs-server

Verify:

systemctl status nfs-server

It should be **active (running)**.

3.159-> 10.124.3.151-3.158


