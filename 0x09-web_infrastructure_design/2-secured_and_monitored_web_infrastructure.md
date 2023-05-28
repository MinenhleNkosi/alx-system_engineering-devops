# Task 2

----
## 2. Secured and monitored web infrastructure
On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`, it must be secured, serve encrypted traffic, and be monitored.

Requirements:

	* You must add:
		* 3 firewalls
		* 1 SSL certificate to serve www.foobar.com over HTTPS
		* 3 monitoring clients (data collector for Sumologic or other monitoring services)
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it
		* What are firewalls for
		* Why is the traffic served over HTTPS
		* What monitoring is used for
		* How the monitoring tool is collecting data
		* Explain what to do if you want to monitor your web server QPS
	* You must be able to explain what the issues are with this infrastructure:
		* Why terminating SSL at the load balancer level is an issue
		* Why having only one MySQL server capable of accepting writes is an issue
		* Why having servers with all the same components (database, web server and application server) might be a problem

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
1. **For every additional element, why are adding it:** Firewalls for Each Server: By adding a firewall for each server, we aim to enhance the security of the infrastructure. Firewalls act as a protective barrier, monitoring and controlling incoming and outgoing network traffic based on predefined security rules. They help prevent unauthorized access, malicious attacks, and potential exploitation of the servers. SSL Certificate for www.foobar.com: The SSL certificate is implemented to enable HTTPS (HTTP over SSL/TLS) for the website www.foobar.com. This ensures secure communication between the server and clients by encrypting the data transmitted. It protects sensitive information, such as login credentials, personal data, and financial details, from interception and unauthorized access.
2. **What are firewalls for:** Monitors Network Traffic: Firewalls monitor incoming and outgoing network traffic, examining data packets based on predefined security rules. They analyze the source, destination, and other parameters of network connections to determine whether to allow or block the traffic. Controls Access: Firewalls control access to the network by defining access policies and rules. They can restrict traffic from unauthorized sources, prevent specific protocols or ports from being accessed, and enforce security policies to protect the network from malicious activities.
3. **Why is the traffic served over HTTPS:** Encryption: HTTPS uses encryption protocols such as SSL/TLS to encrypt the data transmitted between the server and clients. This ensures that the data is secure and protected from eavesdropping, tampering, and unauthorized interception during transit. Data Integrity: HTTPS employs mechanisms to ensure the integrity of the data being transmitted. It uses digital certificates and cryptographic algorithms to verify that the data has not been altered or tampered with during transmission.
4. **What monitoring is used for:** Monitoring is used to proactively detect and diagnose web application performance issues, which includes Performance Optimization, Issue Detection and Troubleshooting, etc.
5. **How the monitoring tool is collecting data:** The monitoring tool collects data by capturing and analyzing logs from various components of the system. In this case, the monitoring tool collects logs from the application server, MySQL database, and Nginx web server.
6. **Explain what to do if you want to monitor your web server QPS:** To monitor your web server's Queries Per Second (QPS) when it handles 1K queries per second, you can: Monitor network traffic to analyze the number of incoming queries per second, Implement application-level monitoring to track the performance and throughput of the web server.

-----
## Problems/Issues
1. **Why terminating SSL at the load balancer level is an issue:** Terminating SSL at the load balancer level can introduce certain issues like: SSL/TLS encryption and decryption require additional processing power and resources, Terminating SSL at the load balancer means that SSL settings and configurations are managed at the load balancer level. This can limit the flexibility and customization options available to individual servers or services behind the load balancer.
2. **Why having only one MySQL server capable of accepting writes is an issue:** Having only one MySQL server capable of accepting writes introduces several issues like If the single MySQL server capable of accepting writes experiences any issues or downtime, it can disrupt the entire application's write operations. This creates a single point of failure, where the loss of the MySQL server affects the availability and reliability of the application.
3. **Why having servers with all the same components (database, web server and application server) might be a problem:** Having servers with all the same components (database, web server, and application server) can present Having identical components on all servers means that any issues or failures affecting one component can potentially impact all servers simultaneously. For example, a bug or vulnerability in a specific version of a web server or database software could affect all servers in the infrastructure, making it difficult to isolate and mitigate the problem.

