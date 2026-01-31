Forward Proxy: If we want to send data to another location and we need to use their location we need to use proxy. Like client from Bangladesh sends some data to Finland Server. So we need to use Finland country proxy so that it seems we are sending data from finland. Proxy works like this.




![[Pasted image 20251022142810.png]]



Now we are going to Reverse Proxy:
User request to reverse proxy server that redirect to different port/page/url. Suppose, you are searching in Amazon website for mobile. you will be redirect to mobile section doesn't matter that portion developed  by paython or javascript or php etc. you didnt know about it because it's redirect to it's targeted server. Reverse Proxy is not so many consuming server. it's job just to redirect to its destination server.

NGINX is a popular Reverse proxy server. user search into NGINX and NGINX decided to redirect to required server.
Caddy is also a reverse proxy server. 


![[Pasted image 20251022170212.png]]


A **reverse proxy** is like a **receptionist** for your web servers.

When someone (a user) sends a request to your website, the reverse proxy **stands in front of your backend servers**, receives that request, and then **forwards it to the right server**.  
Then it gets the server’s response and **sends it back to the user**.

So, users never talk directly to your actual servers — they only talk to the reverse proxy.

### 💬 **Real-life Example (Easy Analogy)**

Imagine you visit a **hotel** 🏨.

- You (client) go to the **reception desk** (reverse proxy).

- The receptionist doesn’t let you walk into every room directly (servers).
 
- Instead, the receptionist asks, “Which service do you need?” and then contacts the right person inside the hotel and gives you the result.

The receptionist = reverse proxy  
Hotel staff = backend servers  
You = client/browser

### **Technical Example**
 
Let’s say you have 3 web servers:

Server 1 → login.example.com
Server 2 → shop.example.com
Server 3 → blog.example.com

You can set up a reverse proxy (for example, Nginx or Apache) on one machine with public access:

User → Reverse Proxy (Nginx) → Internal Servers

When users visit:

example.com/login → proxy sends to Server 1

example.com/shop → proxy sends to Server 2

example.com/blog → proxy sends to Server 3

