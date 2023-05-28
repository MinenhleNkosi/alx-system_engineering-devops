# Task 0

-----
## 0. Simple web stack
A lot of websites are powered by simple web infrastructure, a lot of time it is composed of a single server with a [LAMP stack](https://intranet.alxswe.com/rltoken/YVDX0XsC6XHp0nmezvT9vQ).

On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via `www.foobar.com`. Start your explanation by having a user wanting to access your website.

Requirements:

	* You must use:
		* 1 server
		* 1 web server (Nginx)
		* 1 application server
		* 1 application files (your code base)
		* 1 database (MySQL)
		* 1 domain name `foobar.com` configured with a `www` record that points to your server IP `8.8.8.8`
	* You must be able to explain some specifics about this infrastructure:
		* What is a server
		* What is the role of the domain name
		* What type of DNS record `www is in `www.foobar.com`
		* What is the role of the web server
		* What is the role of the application server
		* What is the role of the database
		* What is the server using to communicate with the computer of the user requesting the website
	* You must be able to explain what the issues are with this infrastructure:
		* SPOF
		* Downtime when maintenance needed (like deploying new code web server needs to be restarted)
		* Cannot scale if too much incoming traffic

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

------
## Explanation
1. **What is a server:** A server is a device, virtual device, computer program, or software that provides functionality and services to other programs or devices, known as clients.
2. **What is the role of the domain name:** The role of a domain name is to serve as a human-readable label that identifies specific Internet resources, such as computers, networks, or services. It provides a more memorable and recognizable name compared to using numerical IP addresses.
3. **What type of DNS record `www` is in `www.foobar.com`:** In the domain name `www.foobar.com`, the `www` part is typically used as a subdomain prefix and does not represent a specific DNS record type. It is mostly used to denote the World Wide Web and is often associated with the A or `CNAMES DNS` record type.
4. **What is the role of the web server:** The role of a web server is to store, process, and deliver website content. It receives requests from clients (usually web browsers) via the HTTP protocol and responds by serving web pages, which typically consist of HTML, CSS, and other related files.
5. **What is the role of the application server:** An application server is responsible for executing server-side code and generating dynamic content. It handles the processing of business logic, database interactions, and other application-specific operations. Application servers support technologies like JSP, PHP, Ajax, and provide an environment for running web applications.
6. **What is the role of the database:** The role of a database is to manage data in an organized and efficient manner. It stores, retrieves, updates, and deletes data, ensuring data integrity and providing mechanisms for data querying and manipulation. Databases are crucial for storing and managing large volumes of structured information.
7. **What is the server using to communicate with the computer of the user requesting the website:** When a user requests a website, the server communicates with the user's computer (client) using the HTTP (Hypertext Transfer Protocol) or its secure variant, HTTPS. The server processes the HTTP request, retrieves the requested web content, and sends it back to the user's computer as an HTTP response. This communication allows the server to deliver web pages and associated resources to the requesting client.

-------
## Problems/Issues
1. **SPOF:** A single point of failure refers to a component or part of the infrastructure that, if it fails, can cause the entire system to fail. In this case, if there is a single server or resource that all other components depend on, it becomes a single point of failure. If that server goes down, the entire system may become inaccessible. To address this, redundancy and fault-tolerant measures should be implemented, such as using load balancers, distributed systems, or backup servers, to ensure high availability and mitigate the risk of a single point of failure.
2. **Downtime when maintenance needed (like deploying new code web server needs to be restarted):** When maintenance tasks, such as deploying new code or updates, are performed on the web server, it often requires restarting the server. During this restart period, the website or application may experience downtime or become temporarily unavailable to users.
3. **Cannot scale if too much incoming traffic:** If the infrastructure is unable to handle a sudden surge in incoming traffic, it indicates a scalability issue. If the existing resources, such as the web server, cannot handle the increased load, the website or application may become slow or unresponsive.

