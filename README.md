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

# Making Your Database Highly Available

Link: https://newsletter.systemdesigncodex.com/p/making-your-database-highly-available

## Redundancy

- **Purpose**: Ensure continuous database operation even if one server fails.
- **Not Backup**: Unlike backups, redundancy involves running multiple active database instances.
- **Cost of Outage**: Can be significantly high, averaging $7,900 per minute.
- **Redundancy Patterns**:
  - **Active-Passive**: One active server handles requests while others stand by.
  - **Active-Active**: Multiple servers handle requests simultaneously.
  - **Multi-Active**: An extension of Active-Active with more complex setups.

## Isolation

- **Goal**: Minimize disaster impact by physically separating database components.
- **Degrees of Separation**:
  - **Server**: Different servers in the same data center.
  - **Rack**: Separate racks within a data center.
  - **Data-Center**: Multiple data centers.
  - **Availability Zone**: Distinct zones within a cloud provider's network.
  - **Region**: Geographically dispersed locations.

# How Rate Limiting Works?

Link: https://newsletter.systemdesigncodex.com/p/how-rate-limiting-works

## How Rate Limiting Works:

1. **Concept**: Limits the number of requests sent to a server.
2. **Implementation**: A rate limiter is used to control traffic to servers or APIs.

## Key Concepts

1. **Limit**: Maximum number of requests allowed in a set time frame (e.g., 600 requests per day).
2. **Window**: The duration for the limit, varying from seconds to days.
3. **Identifier**: A unique attribute (like User ID or IP address) to identify request senders.

## Designing a Rate Limiter

- **Process**:
  1. **Count Requests**: Track the number of requests from a user or IP.
  2. **Limit Exceeded**: If count exceeds the limit, block or restrict further requests.
- **Considerations**:
  - Storage of request counters.
  - Rate limiting rules.
  - Response strategy for blocked requests.
  - Rule change implementation.
  - Maintaining application performance.

## System Components

- **Rate Limiter Component**: Checks incoming requests against the rules and stored data (number of requests made).
- **Rules Engine**: Defines the rate limiting rules.
- **Cache**: Stores rate-limiting data for high throughput and low latency.
- **Response Handling**:
  - Allow request if within limit.
  - Block request if over limit, typically with HTTP status code 429.

## Improvements

- **Silent Drop**: Fool attackers by silently dropping excess requests.
- **Cached Rules**: Enhance performance with a cache for the rules engine and background updates for rule changes.

# Caching

Link: https://newsletter.francofernando.com/p/caching

## Concept of Caching

- **Purpose**: Speeds up data access by storing data temporarily in a fast-access hardware or software layer.
- **Cache Hit**: Data is found in the cache.
- **Cache Miss**: Data is not in the cache and must be fetched from its original location.

## Caching in Distributed Systems

- **Levels**: Hardware, OS, front-end, web apps, databases, etc.
- **Roles**:
  - Reducing latency.
  - Saving network requests.
  - Storing results of resource-intensive operations.
  - Avoiding repetitive operations.

## Types of Caching

- **Application Caching**: Integrated into app code, checks cache before database access. Examples: Memcached, Redis.
- **Database Caching**: Built into databases, requires no code changes, optimizes data retrieval.

## Considerations and Challenges

- **Cache Miss Rate**: High miss rates can add more latency.
- **Stale Data**: Ensuring cache data is up-to-date and relevant.

## Caching Strategies

1. **Cache Aside (Lazy Loading)**:

   - Direct read from cache. If miss, read from DB and update cache.
   - Advantages: Good for read-heavy workloads. Cache only stores necessary data.
   - Disadvantages: Can serve stale data. Initial cache misses.

2. **Read Through**:

   - Interact only with cache. Cache manages data fetching from DB.
   - Simplifies app code but complicates cache implementation.

3. **Write Through**:

   - Writes data to cache and DB simultaneously.
   - Ensures data consistency. Higher write latency.

4. **Write Back (Asynchronous Writing)**:

   - Writes data to cache, then asynchronously to DB.
   - Lower write latency. Good for write-heavy workloads.

5. **Write Around**:
   - Writes directly to DB, cache only stores read data.
   - Good for infrequently read data. Higher read latency for new data.

## Choosing a Cache Strategy

- **Depends on data access patterns**.
- **Cache-Around**: Good for general-purpose, read-intensive applications.
- **Write-Heavy Workloads**: Write-back approaches are beneficial.
- **Infrequent Reads**: Write-around strategy.

## Eviction Policies

- **Manage Limited Cache Space**:
  - FIFO: First in, first out.
  - LIFO: Last in, first out.
  - LRU: Least recently used.
  - MRU: Most recently used.
  - LFU: Least frequently used.
  - RR: Random replacement.

# Database Replication Under the Hood

Link: https://newsletter.systemdesigncodex.com/p/database-replication-under-the-hood

## Statement-based Replication

- **How It Works**: The leader logs every SQL write statement (INSERT, UPDATE, DELETE) and forwards these statements to follower nodes.
- **Advantages**:
  - Efficient in network bandwidth, only SQL statements are transferred.
  - Portable across different database versions.
  - Simpler to implement.
- **Limitations**:
  - Non-deterministic functions (e.g., NOW(), UUID()) yield different values on replicas.
  - Transactions involving auto-incrementing columns must be executed in the same order.
  - Potential unforeseen effects due to triggers or stored procedures.

## Shipping the Write-Ahead Log (WAL)

- **Concept**: The WAL, an append-only sequence of all writes, is shared with follower nodes.
- **Usage**: Common in databases like PostgreSQL.
- **Advantage**: Creates an exact replica of the leader’s data structures.
- **Disadvantage**: Tightly coupled to the storage engine, making it less flexible with database version changes and hindering zero-downtime upgrades.

## Row-Based Replication

- **Functionality**: Uses a logical log showing writes in a row format.
- **Operation Details**:
  - Inserts log new values for all columns.
  - Deletes log identifiers for deleted rows.
  - Updates log identifiers and new values for modified columns.
- **Advantage**: Decouples from the storage engine, allowing backward compatibility and version flexibility between leader and follower databases.

## Choosing Replication Methods

- The choice depends on the specific requirements of the system, such as:
  - Network efficiency.
  - Consistency requirements.
  - Database version compatibility.
- **Statement-based Replication**: Best for simple, less concurrent environments.
- **WAL Shipping**: Suitable for systems where exact replica and data integrity are critical.
- **Row-Based Replication**: Ideal for environments requiring flexibility and compatibility across different database versions.

# Consistent Hashing

Link: https://newsletter.francofernando.com/p/consistent-hashing

## Caching Servers

- **Use Case**: Store frequently accessed data in fast, in-memory caches.
- **Hashing Role**: Ensures identical requests are sent to the same server by hashing request attributes (IP, username, etc.).
- **Challenge**: Maintaining effective caching when servers are added or removed.

## Data Partitioning

- **Purpose**: Distribute data across multiple database servers.
- **Hashing Function**: Data keys are hashed to determine the server where data will be stored.
- **Limitation**: Similar to caching, adding or removing servers complicates data distribution.

## The Hashing Problem

- **Goal**: Map keys (data identifiers or workload requests) to servers efficiently.
- **Desired Properties**:
  - **Balancing**: Equal distribution of keys among servers.
  - **Scalability**: Easily adding or removing servers with minimal reconfiguration.
  - **Lookup Speed**: Quickly finding the server for a given key.

## Naïve Hashing Approach

- **Method**: Number servers, use `hash(key) % N` to assign keys to servers.
- **Drawback**: Not scalable. Changing server count (N) requires remapping all keys.

## Consistent Hashing

- **Concept**: Treat hash values as a circular space. Map keys and servers onto this circle.
- **Operation**: Assign each key to the nearest server on the circle in a clockwise direction.
- **Advantages**:
  - Only a fraction of keys need remapping when adding/removing servers.
  - Better scalability.
- **Issue**: Does not guarantee even key distribution (balancing).

## Virtual Nodes Solution

- **Strategy**: Introduce replicas or virtual nodes for each server on the hash circle.
- **Benefits**:
  - Better balancing due to smaller ranges and more uniform key distribution.
  - Faster rebalancing when servers are added or removed.
  - Support for server fault tolerance and heterogeneity.
- **Implementation**: Assign more virtual nodes to more powerful servers for load balancing.

# Why Replication Lag Occurs in Databases

Link: https://newsletter.systemdesigncodex.com/p/why-replication-lag-occurs-in-databases

- **Concept**: Replication Lag is the delay between a write operation on the leader node and its replication on follower nodes in a database system.

- **Leader-based Replication Setup**:

  - Writes are processed by a single node (leader).
  - Read queries can be served by any replica (follower).
  - Common in systems with more reads than writes.

- **Asynchronous vs. Synchronous Replication**:

  - **Synchronous**: All replicas must confirm write operations, causing potential unavailability if a replica is down.
  - **Asynchronous**: Allows distribution of reads across followers, but can lead to outdated reads if a follower lags.

- **How Replication Lag Occurs**:

  1. User A updates data on the leader node.
  2. Leader sends replication data to followers.
  3. User B reads from a follower (replica 2) before it's updated, receiving outdated information.
  4. Replica 2 eventually gets updated.

- **Implications**:

  - Lag duration varies from fractions of a second to minutes.
  - Causes temporary data inconsistencies (eventual consistency).
  - Large lags can significantly impact application performance.

- **Challenge**: Managing replication lag to minimize data inconsistencies and ensure efficient operation.

# Problems Caused by Database Replication

Link: https://newsletter.systemdesigncodex.com/p/problems-caused-by-db-replication

1. **Vanishing Updates**

   - **Scenario**: User updates data on the leader node, but a subsequent read request to a lagging replica shows outdated data.
   - **Problem**: User experiences frustration as their updates appear to vanish.
   - **Solution**: Implement read-after-write consistency. Methods include:
     - Reading user-modified data from the leader.
     - Tracking recent writes with timestamps.
     - Monitoring and limiting queries on lagging replicas.

2. **Going Backward in Time**

   - **Issue**: User sees an update (e.g., a new comment) and then it disappears upon refreshing, due to a lagging replica.
   - **User Experience**: Confusion and inconsistency.
   - **Solution**: Ensure Monotonic Reads.
     - Users always read from the same replica.
     - Use hashing based on User ID for replica selection.

3. **Violation of Causality**
   - **Problem**: In sharded databases, replication lag causes sequence disorder in communication (e.g., a reply appears before the original message).
   - **Result**: Appears as if cause and effect are reversed.
   - **Solution**: Provide consistent prefix reads.
     - Ensures writes are read in the order they were made.

# How Request Coalescing Works

Link: https://newsletter.systemdesigncodex.com/p/how-request-coalescing-works

**Concept**: Request Coalescing is a technique for optimizing database queries by reducing redundant requests for the same data.

**Application**: Successfully used by Discord to manage trillions of messages efficiently.

**Functionality**:

1. **Setup**: Involves intermediary data services between the API layer and the database.
2. **Process**:
   - When the first request is made, a worker task is initiated in the data service.
   - Subsequent requests for the same data subscribe to this existing task.
   - The worker task queries the database once and returns the result to all subscribers simultaneously.

**Differences from Caching**:

1. **Request Initiation**: In request coalescing, only the first request triggers a database query. Subsequent ones wait for its result. In caching, all requests would hit the cache.
2. **Use with Caching**: Request coalescing can complement caching by reducing the number of hits to the cache.

**Internal Working (Based on Discord's Implementation)**:

- Each worker task maintains a local state with requests and a list of requesters.
- Responses are propagated to all waiting requesters upon arrival.

**Applicability**:

- Request Coalescing is particularly useful for systems with high concurrency and redundant requests.
- The necessity of this technique depends on the scale and specific challenges of the system.

# How to Migrate a MySQL Database

Link: https://newsletter.systemdesign.one/p/how-to-migrate-a-mysql-database

**Context**: Tumblr's MySQL database, spanning 21 terabytes and 60+ billion rows across 200+ servers, necessitated a migration strategy that minimizes user impact.

**Challenges**:

- Maintaining high availability and scalability.
- Minimizing downtime and user impact during migration.

**Strategies Used**:

1. **CQRS Pattern (Command and Query Responsibility Segregation)**:

   - Separated read and write operations for the database.
   - Ensured continuous read availability during migration.

2. **Leader-Follower Replication**:

   - Leader in a remote data center handled read-write operations.
   - Local data center had followers for handling read requests.
   - Used persistent connections to reduce latency issues.

3. **Database Proxy (ProxySQL)**:
   - Positioned in the local data center.
   - Maintained persistent connections to the remote leader.
   - Enabled connection pooling, improving performance and reducing disconnections.

**Migration Process**:

1. **Preparation**:
   - Stored metadata of leaders, followers, and proxies in each data center.
2. **Migration Execution**:
   - Shifted the database leader from Data Center A to B.
   - Automated tools redirected followers and proxies to the new leader.
3. **Outcome**:
   - Followers continued serving read requests.
   - Write requests were briefly halted or buffered, resulting in minimal user impact.

**Consideration for Further Improvement**:

- **Leader-Leader Replication**: Could enhance write availability but poses a risk of data conflicts.
- **Reason for Non-Use**: Potential conflicts might be why Tumblr opted against this approach.

# Durability

Link: https://newsletter.francofernando.com/p/durability

**Core Objective**: Durability, ensuring data is not lost despite failures like power outages, system crashes, or hardware issues.

### Single-Node Database Persistence

1. **Durability Method**: Data is written to nonvolatile storage (hard drive, SSD).
2. **Transaction Processing**:
   - **Log Writing**: Data first written to a log file before making actual data updates.
   - **Update Execution**: After log entry, the database updates the actual data.
   - **Role of Log**: Enables reprocessing of transactions to restore consistent state post-failure.
   - **Efficiency**: Log writing is fast due to its append-only nature, minimizing seek time.

### Distributed Database Persistence

1. **Complexity**: Higher due to the need for coordination across multiple servers.
2. **Two-Phase Commit Protocol**:
   - **Coordinator Role**: A designated server coordinates the commit process.
   - **Process**:
     - Coordinator sends commit instruction to all participant servers.
     - Waits for acknowledgments from all participants.
     - Finalizes the transaction with a commit or rollback based on responses.

# Redis

Link: https://newsletter.francofernando.com/p/redis

**Redis Overview**:

- Redis stands for REmote DIctionary Server.
- It's an open-source, key-value database store.
- Functions as a data structure server, supporting various data structures like Strings, Lists, Sets, Hashes, Sorted Sets, and HyperLogLogs.

**History**:

- Created by Salvatore Sanfilippo in the late 2000s.
- Developed to address scaling issues with MySQL in real-time analytics.
- Gained popularity and wide adoption due to its efficiency and flexibility.

**Operations and Data Types**:

- Basic operations include `GET` and `SET`.
- Supports diverse data structures, each with specific use cases and operations.

**Redis Architectures**:

1. **Single Instance**: Simplest form, running on the same or a separate server.
2. **Replicated Instances**: Primary instance replicated across secondary instances for parallel read requests and backup.
3. **Sentinel**: Manages high availability, monitoring, and failure handling.
4. **Cluster**: Distributes data across multiple machines using sharding.

**Data Persistency**:

- Offers two methods:
  - RDB (Redis Database Backup): Snapshot-based backups.
  - AOF (Append Only File): Logs every change for more recent backups.
- Choice between RDB and AOF depends on the need for speed vs. data recency.

**Single-thread Model**:

- Utilizes a single-threaded model for operations, avoiding multi-threading overhead.
- Performance typically limited by memory and network, not CPU.

**Use Cases**:

- **Database**: As a primary key-value store.
- **Cache**: For storing frequent queries or caching API requests.
- **Pub/Sub**: For scalable and fast messaging systems.

# Salt and Pepper

Link: https://newsletter.francofernando.com/p/salt-and-pepper

### 1. **Hashing**

- **Method**: Converts plain text passwords into a random string of characters.
- **Process**: User's password is hashed and compared with the stored hash during login.
- **Common Algorithms**: MD5, SHA family. However, these are vulnerable to rainbow table attacks.

### 2. **Salting**

- **Purpose**: Enhances hashing by defending against pre-computation attacks like rainbow tables.
- **Implementation**:
  - Generate a unique salt for each password.
  - Combine salt with the password and hash the result.
  - Store the salt in plain text and the hashed password in the database.
- **Validation Process**:
  1. Retrieve the salt from the database.
  2. Combine entered password with salt and hash.
  3. Compare with stored hash for validation.
- **Uniqueness**: Ensures each stored hash is unique, even for identical passwords.

### 3. **Peppering**

- **Function**: Adds an extra layer of security to salting.
- **Mechanism**:
  - Add a pepper value to the password before hashing.
  - The pepper is not stored in the database.
- **Login Process**:
  - Attempt combinations of password and pepper until a match is found.
- **Benefit**: Significantly increases the effort required for brute force attacks.

**Key Takeaways**:

- **Combining Techniques**: Using both salting and peppering provides robust protection.
- **Importance of Uniqueness**: Unique salts and peppers make each hash distinct.
- **Updating Practices**: Continuously update and improve password storage methods to counteract new hacking techniques.

# Moving from Monolithic to Microservices

Link: https://newsletter.systemdesigncodex.com/p/from-monolithic-to-microservices

### 1. **Modular Monolith Approach**

- **Concept**: Incorporates modular design within a monolithic architecture.
- **Characteristics**:
  - Loosely-coupled modules.
  - Well-defined boundaries.
  - Explicit dependencies.
- **Structure**: Application divided into independent modules.
- **Deployment**: Still maintains single application deployment.
- **Advantages**:
  - Streamlines development and maintenance.
  - Offers microservices-like benefits without associated complexities.

### 2. **Evolution to Vertical Slice Architecture**

- **Design Shift**: From horizontal layers to vertical slices of business functionality.
- **Benefits**:
  - Scoped changes to specific business areas.
  - Easier feature addition and modification.
- **Microservices Potential**: Vertical modules can gradually evolve into independent microservices.
- **Learning Opportunity**: Provides insights into domain and functional splits.

### Key Takeaway

- **Balance**: No inherent superiority of microservices over monoliths or vice versa.
- **Evolutionary Approach**: Adapt the architecture to evolving application needs.
- **Pragmatism**: Choose the architecture that best suits the project's requirements and context.

# The Secret Trick to High-Availability

Link: https://newsletter.systemdesigncodex.com/p/the-secret-trick-to-high-availability

### Strategies for Static Stability

1. **Active-Active High Availability**:

   - **Implementation**: Distribute traffic across instances in multiple Availability Zones (AZs).
   - **Example**: If two instances are needed, create three (50% over-provisioning).
   - **Benefit**: Maintains full capacity even if an entire AZ fails.

2. **Active-Passive High Availability**:
   - **Use Case**: For stateful services like databases.
   - **Setup**: Primary instance in one AZ and a standby in another.
   - **Function**: Standby becomes primary if the original primary AZ goes down.

### Criticism and Justification

- **Criticism**: Viewed as resource wasteful due to over-provisioning.
- **Justification**:
  - Essential for mission-critical applications where downtime is unacceptable.
  - Used by major cloud services like AWS (EC2, S3, RDS) to prevent outages.

### Key Takeaway

- **Outages as a Norm**: Disruptions are inevitable; planning for them is crucial.
- **Risk Management**: Over-provisioning is a strategic choice to mitigate downtime risks.
- **Context-Dependent**: The level of static stability required varies based on the system's criticality.

Static stability, while resource-intensive, is a fundamental approach for ensuring continuous operation in high-stake environments where reliability and uptime are non-negotiable.

# 4 Types of NoSQL Databases

Link: https://newsletter.systemdesigncodex.com/p/4-types-of-nosql-databases

### 1. **Document Databases**

- **Examples**: MongoDB, Couchbase, RavenDB.
- **Data Storage**: In the form of JSON, BSON, or XML documents.
- **Advantages**: Align closely with domain-level data objects in applications.
- **Use Case**: Ideal for projects requiring a structure close to application data.

### 2. **Key-Value Store**

- **Examples**: Redis, etcd, DynamoDB.
- **Structure**: Data stored as key-value pairs.
- **Simplicity**: Resembles a two-column table (key and value).
- **Use Cases**: Caching, shopping carts, user profiles.

### 3. **Column-Oriented Database**

- **Examples**: Apache Cassandra, Apache HBase.
- **Storage Method**: Data stored in columns rather than rows.
- **Advantages**: Efficient for analytics and aggregations on specific columns.
- **Considerations**: Not strongly consistent; write operations can be complex.

### 4. **Graph Databases**

- **Examples**: Neo4j, Amazon Neptune.
- **Concept**: Focuses on relationships between data elements (nodes and links).
- **Strengths**: Eliminates the need for multiple table joins as in SQL databases.
- **Use Cases**: Knowledge graphs, social networks, map-like applications.

### Decision Guide:

- **Document DBs**: Versatile, suitable for most applications traditionally using SQL.
- **Key-Value Stores**: For applications requiring fast read/write access to data items.
- **Column-Oriented**: Analytics and operations on large datasets.
- **Graph Databases**: Applications where relationships are central to the data model.
