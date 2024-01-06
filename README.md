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
