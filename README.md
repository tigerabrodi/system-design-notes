# CAP Theorem with Tom the Prankster

Link: https://newsletter.systemdesigncodex.com/p/cap-theorem

1. **Essential Elements**: Consistency, Availability, Partition Tolerance.
2. **Partition Tolerance**: Must-have due to inherent unreliability in communication networks.
3. **Choice between Consistency and Availability**:
   - **Consistency**: All nodes see the same data at the same time. Requires a trade-off with availability.
   - **Availability**: Ensures that the system is always operational, but might compromise on having the latest data across all nodes.

# The Inevitable Law Governing Software Design

Link: https://newsletter.systemdesigncodex.com/p/the-inevitable-law-governing-software-design

- **Basic Principle**: The structure of a software system reflects the communication structure of its creating organization.
- **Example**: In a company with inventory, invoicing, and shipping departments, the software will likely have separate systems for each, mirroring these divisions.
- **Implications**:
  - Software integration quality depends on how well these departments communicate.
  - Better communication leads to more effective and integrated software modules.
- **Strategies for Addressing Conway’s Law**:
  1. **Acknowledge It**: Recognize its impact on software design.
  2. **Structure Teams Effectively**: Place teams working on similar systems close to each other for better communication.
  3. **Avoid Dividing by Technology**: Instead of splitting teams by tech layers (front end, back end), focus on business features for smoother collaboration.
  4. **Use Architectural Insights**: Align team structures with desired software architecture, understanding that organizational decisions influence software design.

# The Ingredients to Delicious Software

Link: https://newsletter.systemdesigncodex.com/p/the-ingredients-to-delicious-software

1. **Scalability**:

   - Ability to handle increased workload efficiently.
   - Important to identify the point where scaling becomes cost-ineffective.

2. **Latency & Throughput**:

   - Latency: Time taken to respond to a request (e.g., time to serve a cheese sandwich).
   - Throughput: Number of requests handled in a given time (e.g., serving multiple customers).

3. **Availability and Consistency**:
   - Availability: Ability to operate despite issues (e.g., with one cook absent).
   - Measured in 'nines' (e.g., 99.9% availability).
   - Consistency: Synchronization of information across different parts of the system (e.g., order copies being in sync).

# What happens when you type a URL into your browser?

Link: https://blog.bytebytego.com/p/what-happens-when-you-type-a-url

When you type a URL into your browser:

1. **URL Parsing**: The browser identifies the HTTP protocol, domain, path, and resource.
2. **DNS Lookup**: It searches for the IP address of the domain, checking various caches.
3. **TCP Connection**: Establishes a connection with the server.
4. **HTTP Request**: Sends a request for the specific resource.
5. **Server Response**: The server sends back the requested content.
6. **Rendering**: The browser displays the webpage.

# How does CDN work?

Link: https://blog.bytebytego.com/p/how-does-cdn-work

1. **Domain Name Lookup**:

   - Bob enters `www.myshop.com` in his browser.
   - The browser checks the local DNS cache for the domain.

2. **DNS Resolver**:

   - If not in the local cache, the browser contacts the DNS resolver (usually via the ISP).

3. **Recursive Domain Resolution**:

   - The DNS resolver performs recursive resolution for `www.myshop.com`.

4. **CDN Integration**:

   - Instead of pointing directly to the London server, the authoritative name server redirects to a CDN domain (`www.myshop.cdn.com`).

5. **Load Balancer Query**:

   - The DNS resolver queries the CDN load balancer domain (`www.myshop.lb.com`).

6. **Optimal Server Selection**:

   - The CDN load balancer selects the best CDN edge server based on factors like the user’s location and server load.

7. **Content Delivery**:

   - The browser connects to the chosen CDN edge server to load content.
   - The content includes static (e.g., images, videos) and dynamic elements.
   - If content is not on the edge server, it's fetched from higher-level CDN servers or the origin server in London.

8. **CDN Network**:
   - This process is part of a geographically distributed CDN network for efficient content delivery.

# Time complexity

Link: https://newsletter.francofernando.com/p/time-complexity

1. **Purpose**: Time complexity evaluates how an algorithm's performance scales with the size of the input data.

2. **Types of Complexity**:

   - **Worst-Case Complexity**: Maximum number of steps for any input of size `n`. Most commonly used as it provides guarantees about the algorithm's upper limit.
   - **Best-Case Complexity**: Minimum number of steps for any input of size `n`.
   - **Average-Case Complexity**: Average number of steps over all possible instances of input size `n`.

3. **Big Oh Notation**: Simplifies the expression of an algorithm's worst-case complexity by focusing on growth rates rather than precise step counts.

4. **Common Complexity Classes**:
   - **Constant - O(1)**: Time is independent of input size (e.g., adding two numbers).
   - **Logarithmic - O(log n)**: Each step cuts the problem size in half (e.g., binary search).
   - **Linear - O(n)**: Time grows linearly with input size (e.g., finding max in an array).
   - **Superlinear - O(n log n)**: Combines linear and logarithmic growth (e.g., Quicksort, Mergesort).
   - **Quadratic - O(n^2)**: Time grows with the square of input size (e.g., insertion sort).
   - **Cubic - O(n^3)**: Involves triple nested loops (e.g., certain dynamic programming algorithms).
   - **Exponential - O(c^n)**: Time doubles with each addition to input size (e.g., enumerating subsets).
   - **Factorial - O(n!)**: Time grows with the factorial of input size (e.g., generating permutations).

# 8 Reasons Why WhatsApp Was Able to Support 50 Billion Messages a Day With Only 32 Engineers

Link: https://newsletter.systemdesign.one/p/whatsapp-engineering

1. **Single Responsibility Principle**:

   - Focus on core feature: Messaging.
   - Avoided feature creep and unnecessary functionalities.
   - Prioritized reliability above all.

2. **Technology Stack**:

   - Chose Erlang for server functionalities due to its scalability and support for hot-loading.
   - Erlang's efficient threading and context-switching mechanisms contributed to performance.

3. **Utilizing Existing Solutions**:

   - Leveraged open-source solutions like Ejabberd, an Erlang-based messaging server.
   - Customized existing solutions to fit specific needs.
   - Integrated third-party services for functionalities like push notifications.

4. **Cross-Cutting Concerns**:

   - Emphasized aspects like monitoring and alerting for service health.
   - Implemented Continuous Integration and Continuous Delivery for software development.

5. **Scalability Strategies**:

   - Adopted diagonal scaling, combining horizontal and vertical scaling methods.
   - Ran servers on FreeBSD, optimized for handling millions of connections.
   - Overprovisioned servers for handling traffic spikes and potential failures.

6. **Continuous Improvement (Flywheel Effect)**:

   - Regularly measured performance metrics to identify and eliminate bottlenecks.
   - Maintained a cycle of continuous feedback and improvement.

7. **Focus on Quality**:

   - Conducted load testing to identify and address single points of failure.
   - Used simulated production traffic for realistic testing.

8. **Small Team Size**:
   - Kept the engineering team small (32 engineers) to maintain efficiency and reduce communication overhead.

# This Is How Quora Shards MySQL to Handle 13+ Terabytes

Link: https://newsletter.systemdesign.one/p/mysql-sharding

1. **Vertical Sharding**:

   - **Implementation**: Separating tables into different servers (leader-follower model).
   - **Purpose**: Enhances write scalability.
   - **Challenges**: Replication lag, transactional limitations, and potential performance issues for large tables.

2. **Horizontal Sharding**:

   - **Reasons for Adoption**: Addressing challenges with large tables such as schema changes and error risks.
   - **Approach**: Splitting a logical table into multiple physical tables.

3. **Key Decisions in Horizontal Sharding**:
   - **Build vs. Buy**: Opted to build their own sharding solution, reusing vertical sharding logic.
   - **Shard Level**: Focused on sharding at the table level due to extensive use of secondary indexes.
   - **Sharding Method**: Chose range-based partitioning, favoring common range queries.
   - **Metadata Management**: Stored shard metadata in Apache Zookeeper.
   - **Database API**: Modified to handle sharding columns and keys, enhancing security against SQL injections.
   - **Sharding Column Selection**: Based on latency sensitivity and query per second (QPS) considerations.
   - **Cross-Shard Indexes**: Used to optimize non-sharding column queries, though with potential performance and consistency trade-offs.
   - **Number of Shards**: Maintained a lower count to reduce latency in non-sharding column queries.
