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
