## Chapter 4: General System Design
For a Machine Learning role, you may not need deep expertise in general software engineering system design. However, as a senior engineer, it’s important to understand the high-level components of typical software systems, the design choices available, and their trade-offs. In particular, understanding non-functional requirements and how different design choices impact them is crucial. As a senior engineer, you should be familiar with various system architecture options, their pros and cons, and how different components fit together to deliver a seamless user experience.

### **System Design Trade-Offs**  

When designing a system, there are various trade-offs to consider depending on the use case and requirements. Below are some key trade-offs with examples:  

1️⃣ **Availability vs. Consistency**  
   - **Availability-focused:** Stale data is acceptable (e.g., **CDNs, social networks** where eventual consistency is sufficient).  
   - **Consistency-focused:** Accuracy is critical (e.g., **financial transactions, banking systems** where strong consistency is required).  

2️⃣ **Latency vs. Throughput**  
   - **Low Latency:** Time per operation matters (e.g., **real-time applications, gaming, high-frequency trading**).  
   - **High Throughput:** Number of operations matters more than individual response time (e.g., **big data analytics, batch processing**).  

3️⃣ **Horizontal vs. Vertical Scaling**  
   - **Horizontal Scaling (Scaling Out):** Adding more machines (e.g., **distributed databases, cloud-based microservices**).  
   - **Vertical Scaling (Scaling Up):** Increasing the power of a single machine (e.g., **high-performance computing, monolithic applications**).  

4️⃣ **Caching vs. Disk Storage**  
   - **Caching (Memory-Based):** Fast access but limited storage (e.g., **Redis, Memcached**).  
   - **Disk Storage (Persistent):** Slower but scalable and persistent (e.g., **databases, object storage**).  

5️⃣ **Push vs. Pull (Polling) Architecture**  
   - **Push Model:** Data is sent when updates occur (e.g., **real-time notifications, WebSockets**).  
   - **Pull/Polling Model:** Clients request updates at intervals (e.g., **RSS feeds, scheduled API calls**).  

6️⃣ **Asynchronous vs. Synchronous Processing**  
   - **Asynchronous:** Improves efficiency, non-blocking (e.g., **background jobs, event-driven architectures**).  
   - **Synchronous:** Simpler but can be slow and blocking (e.g., **traditional HTTP requests**).  

7️⃣ **Real-Time vs. Batch Processing**  
   - **Real-Time Processing:** Immediate data processing (e.g., **streaming analytics, fraud detection**).  
   - **Batch Processing:** Data is processed periodically (e.g., **ETL jobs, nightly data aggregation**).  

Each trade-off should be evaluated based on system goals, performance requirements, and cost considerations.

These videos cover essential concepts for system design interviews—highly recommended!

[Design Spotify](https://www.youtube.com/watch?v=_K-eupuDVEc&list=PLf3F6FcQwgqEpnucyupbIqzxyvFOz9uDq)

[Design TikTok](https://www.youtube.com/watch?v=NHqdG-aZxOk&list=PLf3F6FcQwgqEpnucyupbIqzxyvFOz9uDq&index=2)

If you want to explore more system design problems and architectures beyond recommendation and ranking systems, check out these links:

[A quick resource](https://www.hellointerview.com/learn/system-design/in-a-hurry/introduction)

[A more comprehensive resource](https://www.hiredintech.com/system-design/)
