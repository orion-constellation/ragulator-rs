# ragulator-rs

A rust based implementation of a new ragulator tool based on common configuration of RAG at present. Using a reward function it will aim for a target until it lands on it for the optimal results across a fixed range of features. 5 total supported at the moment as the max for any result.


## Why?
So many choices, chunking size etc. RAGulator seamlessly blends Rust's high performance with Python's AI ecosystem, incorporating Cloudflare's AI Gateway and Portkey for unparalleled efficiency. This powerhouse optimizes AI tasks in real-time, utilizing a cutting-edge toolset to adapt and learn swiftly.

### Core Technology stack:

### Rust:
- Model the RAG system as a Graph
- Implement Genetic Algorithms (search for libraries.)
- Define RL environment and the agent within it (search for libraries)
- Establish concurrency between the two processes.
-  Use genetic algorithms to generate initial diverse configurations, then apply reinforcement learning to fine-tune these configurations, learning from each iteration to improve decision-making on graph modifications.
-  Run an LLM across it for summary of the nodes. Relationships should move quickly from there.
-  Relationship strength will be arrived at in no time.

## Contact? 
**core@synavate.tech
**
  

