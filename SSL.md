## What is “Encryption”?

**Encryption** = hiding data so that only authorized people can read it.

Example:  
You send “HELLO” → encryption turns it into something unreadable like `A73#@L90`.  
Only someone with the **key** can unlock and see the real message.

---

## 🧩 There are 2 main types of Encryption:

### **1️⃣ Symmetric Encryption**

👉 **Same key** is used to **encrypt** and **decrypt** data.

### **2️⃣ Asymmetric Encryption**

👉 **Different keys** are used — one to **encrypt**, and another to **decrypt**.

---

# 🔒 1. Symmetric Encryption (Same Key)

### 💡 Meaning:

Both sender and receiver use the **same secret key**.

📦 Example:

- You lock a box with a key 🔑.
    
- You send the box to your friend.
    
- Your friend **must have the same key** to open it.
    

### 🧮 Example in Computers:

You and your friend both know a secret key `abc123`.  
You type:

Plain text: HELLO
Encrypted with key 'abc123' → 9FD83A@$

Your friend uses **same key 'abc123'** to decrypt it back to “HELLO”.

### ⚙️ Common Algorithms:

- AES (Advanced Encryption Standard)
    
- DES (Data Encryption Standard)
    
- Blowfish
    

### ✅ Pros:

- Fast and simple
    
- Great for large data (e.g., files, backups)
    

### ❌ Cons:

- You must **safely share the key** first — if someone steals it, they can decrypt everything.
    

---

# 🔑 2. Asymmetric Encryption (Different Keys)

### 💡 Meaning:

There are **two keys**:

- **Public key** → used to **encrypt**
    
- **Private key** → used to **decrypt**
    

They are mathematically linked, but you can’t guess one from the other.

📦 Example:

- You have a **mailbox** with a public slot to drop letters (public key) and a private key to open it.
    
- Anyone can send you a letter, but only you can open the box.
    

---

### 🧮 Example in Computers:

You have:

- **Public key** → share with everyone
    
- **Private key** → keep secret
    

When your friend wants to send you a message:

1. They **encrypt** it using **your public key**.
    
2. Only **your private key** can **decrypt** it.
    

Even if hackers see the message, they can’t read it without your private key.

### ⚙️ Common Algorithms:

- RSA
    
- ECC (Elliptic Curve Cryptography)
    
- DSA
    

### ✅ Pros:

- No need to share the private key.
    
- Very secure for communication and authentication (e.g., SSL, SSH, digital signatures).
    

### ❌ Cons:

- Slower than symmetric encryption.
    
- Not suitable for encrypting huge files directly.
    

---

# 🔐 Example in Real Life: HTTPS (Website Security)

When you visit a secure website (🔒 HTTPS):

1. Your browser and the website use **asymmetric encryption** first — to **safely exchange a secret key**.
    
2. Then, they switch to **symmetric encryption** to send data fast.
    

✅ This combination = **Best of both worlds**

---

# 🧾 Summary Table

|Feature|Symmetric Encryption|Asymmetric Encryption|
|---|---|---|
|🔑 Keys used|One key (same for encrypt/decrypt)|Two keys (public + private)|
|🔒 Key sharing|Must share secret key securely|Public key can be shared freely|
|⚡ Speed|Very fast|Slower|
|🧰 Common use|File encryption, data at rest|Secure communication, SSL, SSH|
|🔧 Algorithms|AES, DES, Blowfish|RSA, ECC, DSA|
|📦 Example|Encrypting a backup file|Sending secure email (PGP), HTTPS|


### Now We Will Learn SSL CERTIFICATE

for secure our connection using both Symmetric and Asymmetric encryption, we can use SSL Certification. Because using Symmetric encryption both client and user use same key so that, it's a high chance to leak data or change Data by MMA(Man in the middle attacker) person. Moreover, if we use Asymmetric encryption the user dont know the sender(client data) details. so there is a high chance to 