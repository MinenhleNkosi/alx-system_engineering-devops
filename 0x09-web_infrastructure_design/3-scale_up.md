# Task 3

-----
## 3. Scale up
Readme
	* [Application server vs web server](https://intranet.alxswe.com/rltoken/toFi_SdFHyi2MaELB8ekqw)

Requirements:

	* You must add:
		* 1 server
		* 1 load-balancer (HAproxy) configured as cluster with the other one
		* Split components (web server, application server, database) with their own server
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
1. **For every additional element, why are adding it:** we have added one server and one load balancer. Adding the new server has allowed us to separate each component (web server; Nginx, Application server; code base and Database; MySQL) in there own server and yet having one extra server with all the components to serve as a backup if any of the components or server fails. Each server is being monitored and has a firewall. We have also added an extra load balancer that will assist in handling more traffic across the whole infrastructure.
