**NETWORK CONCEPTS**

---

**Contents**:

- [Forward proxy (or simply proxy)](#forward-proxy-or-simply-proxy)
- [Reverse proxy](#reverse-proxy)
- [PEP333(3)](#pep3333)
- [ASGI and WSGI](#asgi-and-wsgi)
- [To learn about](#to-learn-about)

---

# Forward proxy (or simply proxy)
Forward proxy or simply proxy is used within the client network to hide the real IP of the client with imposed firewall restrictions /content filtering on a common proxy server. in short : A proxy server is a go‑between or intermediary server that forwards requests for content from multiple clients to different servers across the Internet. Proxy server can act as a cache to serve requests from clients is the same content is requested.

# Reverse proxy
Reverse proxy is mainly used by server admins for load balancing and high availability.There could be one or many servers serving the request behind the reverse-proxy. The server is unaware of where requests are coming from.

Common uses for a reverse proxy server include:

<details><summary>Load balancing</summary><p>A reverse proxy server can act as a “traffic cop,” sitting in front of your backend servers and distributing client requests across a group of servers in a manner that maximizes speed and capacity utilization while ensuring no one server is overloaded, which can degrade performance. If a server goes down, the load balancer redirects traffic to the remaining online servers.</p></details>

<details><summary>Web acceleration</summary><p>Reverse proxies can compress inbound and outbound data, as well as cache commonly requested content, both of which speed up the flow of traffic between clients and servers. They can also perform additional tasks such as SSL encryption to take load off of your web servers, thereby boosting their performance.</p></details>

<details><summary>Security and anonymity</summary><p>By intercepting requests headed for your backend servers, a reverse proxy server protects their identities and acts as an additional defense against security attacks. It also ensures that multiple servers can be accessed from a single record locator or URL regardless of the structure of your local area network.</p></details>

# PEP333(3)
This is a document that specifies a proposed standard interface between web servers and Python web applications or frameworks, to promote web application portability across a variety of web servers.

# ASGI and WSGI
ASGI (Asynchronous Server Gateway Interface) and WSGI (Web Server Gateway Interface), as the name suggests, both act as bridges between Web Servers and our Python web applications. They are the Python specifications that define how web servers and web applications will interact with each other. Understanding the difference between ASGI and WSGI is crucial for your development learning/

<details><summary>WSGI</summary><p>WSGI stands for Web Server Gateway Interface and is suitable for synchronous programming or application.</p></details>

<details><summary>ASGI</summary><p>ASGI stands for Asynchronous Server Gateway Interface and is suitable for asynchronous applications. It supports handling long-lived connections, WebSockets, and other non-HTTP protocols.</p></details>

> **Reference**: [_Difference Between ASGI and WSGI in Django_ from **GeeksForGeeks.org**](https://www.geeksforgeeks.org/difference-between-asgi-and-wsgi-in-django/)

---

WSGI options:

- Green Unicorn or gunicorn
- Tornado
- CherryPy
- TwistedWeb
- `mod_wgsi` (module)
- `uWSGI`

# To learn about
Understand:

```
Client (http-request) --> Apache-HTTP Server or NGINX (reverse-proxy)--> gUnicorn (WSGI HTTP Server) -->Django(bottlr or flask) --> python code
```