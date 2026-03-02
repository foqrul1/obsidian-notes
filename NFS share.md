## STEP 1 — Install NFS Packages

dnf install -y nfs-utils

---

## ✅ STEP 2 — Enable & Start NFS Service

systemctl enable --now nfs-server

Verify:

systemctl status nfs-server

It should be **active (running)**.


