# Task 1

-------
## 1. Distributed web infrastructure
On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`.

Requirements:

	* You must add:
		* 2 servers
		* 1 web server (Nginx)
		* 1 application server
		* 1 load-balancer (HAproxy)
		* 1 set of application files (your code base)
		* 1 database (MySQL)
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it
		* What distribution algorithm your load balancer is configured with and how it works
		* Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
		* How a database Primary-Replica (Master-Slave) cluster works
		* What is the difference between the Primary node and the Replica node in regard to the application
	* You must be able to explain what the issues are with this infrastructure:
		* Where are SPOF
		* Security issues (no firewall, no HTTPS)
		* No monitoring

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
1. **For every additional element, why you are adding it:** I'm adding a new server to meet the requirements of adding a load balancer for traffic management. It will also assist in eliminating a single point of failure which stands a better chance of occuring if we rely on a single server.
2. **What distribution algorithm your load balancer is configured with and how it works:** The  load balancer is configured with the Round Robin algorithm. The Round Robin algorithm works by distributing incoming requests to the available servers in a sequential manner. Each new request is routed to the next server in the rotation, following a circular pattern. If a server is down or unavailable, the load balancer simply skips it and proceeds to the next server in line.
3. **Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both:** Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both.  In an Active-Passive setup, there is a primary server actively serving traffic while one or more standby or passive servers remain idle, ready to take over if the primary server fails or becomes unavailable.
4. **How a database Primary-Replica (Master-Slave) cluster works:** In a database Primary-Replica (Master-Slave) cluster, the cluster consists of one primary node (master) and one or more replica nodes (slaves). The primary node is responsible for handling read and write operations, while the replica nodes maintain copies of the primary node's data for redundancy and scalability purposes.
5. **What is the difference between the Primary node and the Replica node in regard to the application:** The primary node handles both read and write operations from the application. It is responsible for processing and executing all read and write queries, including insert, update, and delete operations. Replica nodes are primarily used to offload read operations from the primary node. They serve as read replicas that can handle read queries from the application. By directing read queries to replica nodes, the overall read performance and scalability of the database can be improved.

----
## Problems/Issues
1. **SPOF:** The infrastructure described suffers from potential single points of failure. This means that if a critical component or system fails, it could cause a complete disruption of services. For example, if there is only one server serving the application and it experiences a hardware failure, the entire application will become inaccessible.
2. **Security issues (no firewall, no HTTPS):** The infrastructure lacks essential security measures. Without a firewall, the system is exposed to potential attacks and unauthorized access. Firewalls play a crucial role in filtering network traffic, protecting against malicious activities, and enforcing security policies.
3. **No monitoring:** Monitoring is essential for proactively identifying and resolving issues, ensuring system performance, and maintaining uptime. Without monitoring tools and processes in place, it becomes difficult to detect performance bottlenecks, track resource utilization, identify security incidents, or monitor the overall health of the infrastructure.

