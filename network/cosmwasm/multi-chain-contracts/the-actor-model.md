# The Actor Model

The CosmWasm actor model serves as a foundational design pattern. Each actor has its own isolated internal state and communicates with others solely through messages, avoiding direct calls. Key insights from this approach include:



**Loose Coupling:** Actors are coupled mainly by the data format of the messages they exchange, akin to the boundary protocols in REST or RPC. This promotes scalability and interoperability.

**Concurrency and Serialization:** While the model theoretically supports concurrency, in CosmWasm, execution within each actor is serialized, preventing potential threats such as reentrancy attacks. This serialization ensures that an operation is completed fully before the next begins.

**Atomic Execution:** Ensuring multiple contract states change atomically can be challenging. CosmWasm employs an "optimistic update" approach. It executes all operations with the assumption they'll succeed and rolls back if any part fails, ensuring data consistency.

**Security Enhancements:** The model ensures that a contract's internal state remains private, allowing it to dictate valid state transitions. It's a safer paradigm than having unbounded access, which is more susceptible to vulnerabilities.

**Locality Principle:** Actors communicate only with known counterparts. For two actors to interact, an external message must introduce them, laying the foundation for dynamic communication topologies in a distributed setup.

**Cross-chain Communication:** The actor model naturally aligns with Inter-Blockchain Communication (IBC) due to its reliance on message-passing. While this is an advantage, it brings challenges when ensuring atomic execution across different chains.



For a more detailed explanation, read CosmWasm docs [here](https://docs.cosmwasm.com/docs/architecture/actor).
