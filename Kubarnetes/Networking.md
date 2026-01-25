
### 🔌 What is Networking?

**Networking** in computers means connecting two or more devices (like computers, servers, printers, phones) so they can share information with each other.

---

### 🧱 Basic Networking Terms (Beginner Level)

1. **IP Address**:  
    Like a house address for your computer. It helps other devices find it on a network.  
    Example: `192.168.1.10`
    
2. **Router**:  
    A device that connects your home or office network to the internet.
    
3. **Switch**:  
    Like a multi-plug adapter. It connects several devices in a local network so they can talk to each other.
    
4. **LAN (Local Area Network)**:  
    A small network—like inside your home, office, or school.
    
5. **WAN (Wide Area Network)**:  
    A bigger network—like the internet or a company’s global network.
    
6. **MAC Address**:  
    A unique hardware ID for your network device (like your computer’s network card).
    
7. **DNS (Domain Name System)**:  
    Converts names (like google.com) into IP addresses (like `142.250.190.78`) so computers understand.
    
8. **Firewall**:  
    Security system that controls what traffic is allowed in or out of your network.

### 🅰️ 🅱️ 🅲️ **Class A, B, C (IP Address Classes)**

#### 🔹 What’s an IP address again?

Think of it like a phone number for a device on a network.

#### 🔹 What are Classes A, B, and C?

Long ago, IP addresses were grouped into classes (A, B, C) based on how **many devices** you want in a network.

|Class|Starting IPs|Used For|Example|
|---|---|---|---|
|A|1.0.0.0 – 126.255.255.255|Huge networks (like big companies or ISPs)|10.1.2.3|
|B|128.0.0.0 – 191.255.255.255|Medium networks (universities, companies)|172.16.5.4|
|C|192.0.0.0 – 223.255.255.255|Small networks (home, small office)|192.168.1.1|

👉 You don’t need to memorize the full ranges—just remember:

- **Class A** = Big
    
- **Class B** = Medium
    
- **Class C** = Small
    

---

### 🌐 **Private vs Public IP**

#### 📍 Private IP

- Used **inside** your home/office.
    
- Not reachable from the internet.
    
- Examples:
    
    - 192.168.x.x (common in home Wi-Fi)
        
    - 10.x.x.x
        
    - 172.16.x.x – 172.31.x.x
        

📦 **Example**:  
Your laptop at home may have **192.168.0.5** → a private IP.

#### 🌍 Public IP

- Used on the **internet**.
    
- Given by your **Internet Provider (ISP)**.
    
- Unique across the whole world.
    

📦 **Example**:  
Your home Wi-Fi router may have **103.56.245.22** → a public IP.

🔁 Your router shares the public IP and gives private IPs to all your devices at home using something called **NAT** (we’ll explain later if you want!).

---

### 🚪 **Gateway**

This is like the **main door** out of your house (network).  
It connects your local network to other networks (like the internet).

📦 **Example**:  
If your PC IP is `192.168.1.10`, the gateway is often `192.168.1.1` (your router).

---

### 🌍 **DNS (Domain Name System)**

DNS is like the **internet's phonebook**.  
It converts website names into IP addresses.

📦 **Example**:  
You type: `www.google.com`  
DNS translates it into: `142.250.190.78`  
Then your browser connects to that IP.

Common DNS servers:

- Google: `8.8.8.8`
    
- Cloudflare: `1.1.1.1`
    

---

### 🎭 **Subnet Mask**

This tells your computer **which devices are in the same local network** and which are not.

📦 **Example**:  
Your IP is `192.168.1.10`  
Subnet mask: `255.255.255.0`

That means:

- Devices from `192.168.1.1` to `192.168.1.254` are in your **local network**
    
- Others (like `8.8.8.8`) are **outside**, so traffic goes to the **gateway**
    

You can think of subnet mask like a **fence around your house**. Only neighbors inside the fence are in your "local area."

---

### 🧠 Quick Summary:

|Term|Think of it as…|Example|
|---|---|---|
|**Class A/B/C**|Size of the neighborhood|Class C for homes|
|**Private IP**|Address inside your house|192.168.1.5|
|**Public IP**|Your address on the internet|103.54.22.8|
|**Gateway**|Your door to the outside world|192.168.1.1|
|**DNS**|Internet phonebook|8.8.8.8|
|**Mask**|Fence around your house|255.255.255.0|

## ✅ What is a **Subnet Mask**?

A **subnet mask** helps your computer **understand which other devices are in the same local network** and which are **outside** (so it should send data to the gateway/router).

You can think of it like a **fence** around a group of houses:

- Inside the fence = talk directly (same network)
    
- Outside the fence = call the post office (gateway)
    

---

## 👨‍💻 Example Setup (Home Network)

| Device      | IP Address     | Subnet Mask     |
| ----------- | -------------- | --------------- |
| Your PC     | `192.168.1.10` | `255.255.255.0` |
| Your Phone  | `192.168.1.20` | `255.255.255.0` |
| Your Router | `192.168.1.1`  | `255.255.255.0` |

## 🔍 What does `255.255.255.0` mean?

This is the most common subnet mask. Let's break it down:

### IP Address:

`192.168.1.10` → in binary:

11000000.10101000.00000001.00001010

### Subnet Mask:

`255.255.255.0` → in binary:***
11111111.11111111.11111111.00000000

The 1s in the subnet mask mean: This part identifies the network
The 0s mean: This part identifies the host (devices)

### 🧠 So in our example:

- Network portion = `192.168.1`
    
- Host portion = `.10`, `.20`, etc.
    

That means:

- Devices from `192.168.1.1` to `192.168.1.254` are in the **same network**.
    
- If you try to reach `192.168.2.5`, it’s **outside the network**, so traffic goes to the **gateway**

## 🧪 Visual Example

### Network: `192.168.1.0/24`

- Mask: `255.255.255.0`
    
- Range: `192.168.1.1` to `192.168.1.254`
    
- Gateway: `192.168.1.1`
    
- Broadcast: `192.168.1.255`
    

### So:

| Source         | Destination    | Same Network? | Goes through Gateway? |
| -------------- | -------------- | ------------- | --------------------- |
| `192.168.1.10` | `192.168.1.20` | ✅ Yes         | ❌ No                  |
| `192.168.1.10` | `192.168.2.5`  | ❌ No          | ✅ Yes                 |

## 📦 More Subnet Mask Examples

|Subnet Mask|CIDR|Hosts per Network|Use Case|
|---|---|---|---|
|`255.255.255.0`|`/24`|254 hosts|Home, small office|
|`255.255.0.0`|`/16`|65,534 hosts|Medium network|
|`255.0.0.0`|`/8`|16 million+ hosts|Huge networks|
## 🧠 Tip:

In simple terms:

- **More 1s** in mask = **smaller networks** (fewer hosts)
    
- **More 0s** in mask = **larger networks** (more hosts)
    

---

## 🔧 How to Check Your Subnet Mask (Windows)

1. Open Command Prompt (`cmd`)
    
2. Type:
	**ipconfig

You’ll see:

IPv4 Address. . . . . . . : 192.168.1.10
Subnet Mask . . . . . . . : 255.255.255.0
Default Gateway . . . . . : 192.168.1.1**


## 📣 What is a **Broadcast in Networking**?

**Broadcast** means sending a message to **every device in the local network** — all at once.

🗣️ Imagine you're in a classroom. Instead of calling each student by name, the teacher says:

> "Everyone listen!"

That’s a **broadcast** — a message sent to **everyone nearby**.

---

## 🖥️ In Computer Networks:

When one device sends a **broadcast**, every other device in the **same subnet (local network)** hears it.

This is useful for:

- Finding other devices (like printers)
    
- Sending alerts
    
- IP address discovery (like DHCP)
    

---

## 📦 Example

### Your Local Network (Class C / Subnet Mask: 255.255.255.0)

- Network Address: `192.168.1.0`
    
- Usable IPs: `192.168.1.1` to `192.168.1.254`
    
- **Broadcast Address**: `192.168.1.255`
    

So if your computer sends a message to `192.168.1.255`, **all devices** on `192.168.1.x` will receive it.

---

### 🧠 Why Use Broadcast?

- **DHCP**: When your PC starts, it doesn’t know the IP of the DHCP server. So it broadcasts:
    
    > "Is there a DHCP server out there?"
    
- **ARP**: Your PC wants to know the MAC address of a device. It broadcasts:
    
    > "Who has IP 192.168.1.5?"
    

---

## 📋 Summary Table

|Term|Meaning|
|---|---|
|**Broadcast Address**|Special IP used to reach **all devices** in a subnet|
|**Used For**|DHCP, ARP, discovery|
|**Example**|`192.168.1.255` in a `/24` subnet|
|**Who Receives It?**|Every device in the same network|

## ⚠️ Important Notes

- Broadcasts **do not leave** the local network. They **do not go to the internet**.
    
- Too many broadcasts can slow down a network — that's why large networks are split into **smaller subnets**.


## 🔀 **3. Unicast vs Multicast vs Broadcast**

| Type          | Sent To                  | Used For               | Example              |
| ------------- | ------------------------ | ---------------------- | -------------------- |
| **Unicast**   | 1-to-1                   | Most internet traffic  | Sending an email     |
| **Broadcast** | 1-to-all (local only)    | Discovery, DHCP, ARP   | `ping 192.168.1.255` |
| **Multicast** | 1-to-many (select group) | Streaming, video calls | IPTV, Zoom           |


### ✅ Examples

#### 🔹 **Unicast:**

- IP: `192.168.1.10 → 192.168.1.20`
    
- Only device `.20` receives the message.
    

#### 🔹 **Broadcast:**

- IP: `192.168.1.10 → 192.168.1.255`
    
- Every device in the network hears it.
    

#### 🔹 **Multicast:**

- Sent to a special group (e.g., `224.0.0.1`)
    
- Devices **that joined the group** will listen.
    

---

### 🧠 Quick Reminder

|Type|IP Range|
|---|---|
|Unicast|Normal IPs (like `192.168.x.x`)|
|Broadcast|Last IP of subnet (like `192.168.1.255`)|
|Multicast|`224.0.0.0` – `239.255.255.255`|


# OSI Model (Open System Interconnection):

1. Physical Layer
2. Data Link Layer
3. Transport Lay
