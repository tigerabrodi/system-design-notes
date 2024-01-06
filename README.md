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
