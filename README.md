# Load Balancer – System Design Interview Question

When a website becomes extremely popular, the traffic on that website increases, and the load on a single server also increases. The concurrent traffic overloads the single server, causing the website to become slower for the users. To meet the demand of high traffic volumes and return responses quickly and reliably, we need to scale the server. This can be done by adding more servers to the network and distributing all the requests across these servers.


## Important Topics for the Load Balancer – System Design Interview Question

- What is a Load Balancer?
- What will happen if there is No Load Balancer?
- How Load Balancer Works?
- Where Are Load Balancers Typically Placed?
- Types of Load Balancers
- Load Balancing Algorithms
- How to Use Load Balancing During System Design Interviews?

### 1. What is a Load Balancer?

A load balancer is a networking device or software application that distributes and balances the incoming traffic among the servers to provide high availability, efficient utilization of servers, and high performance.

Load balancers are crucial in high-availability systems, especially in cloud computing, data centers, and large-scale web applications. They ensure that incoming traffic doesn't overload a single server, which could result in server crashes or high latency.

### 2. What Will Happen if There is No Load Balancer?

Consider a scenario where an application is running on a single server and the client connects to that server directly without load balancing:


#### Problems without Load Balancer:

- **Single Point of Failure:** If the server goes down, the entire application becomes unavailable, leading to poor user experience.
- **Overloaded Servers:** As the number of requests grows, the server will become overloaded, causing delays and crashes.

To resolve this, we need to add more servers and distribute the requests across a cluster of servers.

### 3. How Load Balancer Works?

To solve the issues of overload and single points of failure, a load balancer can be added in front of the web servers. The load balancer distributes incoming requests across multiple servers, which can handle higher volumes of traffic. 


By ensuring that servers are not overloaded, load balancers minimize latency and maximize throughput. They also monitor the health of servers and distribute requests only to healthy servers, improving reliability.

### 4. Where Are Load Balancers Typically Placed?

Load balancers can be placed in various stages of the network to manage traffic:

- Between the client application/user and the server
- Between the server and the application/job servers
- Between the application servers and the cache servers
- Between the cache servers and the database servers


### 5. Types of Load Balancers

#### 5.1 Based on Configurations

1. **Software Load Balancers:** These are applications or components that run on general-purpose servers. They are flexible and adaptable to different environments.
2. **Hardware Load Balancers:** These are physical appliances that distribute traffic across servers. They are expensive but used as the first point of contact for user requests.
3. **Virtual Load Balancers:** These are implemented as virtual machines (VMs) or software instances in a virtualized environment, distributing traffic across multiple servers.

#### 5.2 Based on Functions

1. **Layer 4 (L4) Load Balancer:** Operates at the transport layer (OSI model), making decisions based on IP addresses and port numbers.
2. **Layer 7 (L7) Load Balancer:** Operates at the application layer (OSI model), making decisions based on content like URLs, HTTP headers, or cookies.
3. **Global Server Load Balancing (GSLB):** Distributes traffic across geographically distributed servers, taking into account server proximity, health, and location.

### 6. Load Balancing Algorithms

Load balancers use different algorithms to decide which server to route a request to. Some common load balancing algorithms include:

1. **Round Robin:** Distributes requests sequentially across servers, but doesn't account for the current load on each server.
2. **Weighted Round Robin:** Similar to Round Robin, but assigns a weighted score to each server, distributing requests based on these weights.
3. **Source IP Hash:** Distributes requests based on the hash value of the client's IP address, ensuring that requests from the same source IP go to the same server.
4. **Least Connection Method:** Directs requests to the server with the fewest active connections, aiming for a balanced load.
5. **Least Response Time Method:** Directs requests to the server with the fastest response time, minimizing latency.

### 7. How to Use Load Balancing During System Design Interviews?

In system design interviews, you'll likely be asked questions about scalability and how to ensure high availability in your application. Here are the key takeaways:

- **Elastic Scalability:** Load balancers improve performance and throughput by enabling elastic scalability. They allow adding or removing servers as needed to handle varying traffic loads.
- **Redundancy and Availability:** By distributing requests across multiple servers, load balancers ensure redundancy, meaning that even if one server goes down, the system remains available.
- **Improved Performance:** Load balancing reduces the load on individual servers, preventing server crashes and reducing response time, which leads to a better user experience.

---

Reference: Geeks for Geeks (https://www.geeksforgeeks.org/load-balancer-system-design-interview-question/)
