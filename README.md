# CAP Theorem with Tom the Prankster

Link: https://newsletter.systemdesigncodex.com/p/cap-theorem

1. **Essential Elements**: Consistency, Availability, Partition Tolerance.
2. **Partition Tolerance**: Must-have due to inherent unreliability in communication networks.
3. **Choice between Consistency and Availability**:
   - **Consistency**: All nodes see the same data at the same time. Requires a trade-off with availability.
   - **Availability**: Ensures that the system is always operational, but might compromise on having the latest data across all nodes.
