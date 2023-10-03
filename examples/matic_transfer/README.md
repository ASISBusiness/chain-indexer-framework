# MATIC_TRANSFER

Matic-transfer is an exemplary project that showcases the usage of Chain Indexer Framework to index all MATIC transfers occurring on the Ethereum blockchain.

## Overview
The project consists of three distinct packages, each serving a specific function:

1. **Producers**: This package acts as the initial entry point for the indexer service. It collects all ethereum blockchain data from a starting block as per env and streams it into Kafka without any discrimination.

2. **Transformers**: The Transformers package consumes the blockchain data from the Kafka stream generated by the producers. It then filters out all MATIC transfers and reproduces these events to a dedicated topic within the Kafka stream.

3. **Consumers**: Consumers are responsible for subscribing to the event-specific Kafka stream and persisting the data into a database. Additionally, they expose endpoints that allow clients to retrieve the data according to their specific requirements.

This serves as a useful reference for understanding how Chain Indexer Framework can be effectively utilized to manage and process blockchain data efficiently along with reorg handling.


## How to Build

- Make sure you run kafka inside your docker and mongoDB. steps can be found [here](../README.md)
  
- Run [Producer](./producer/README.md)

- Run [Transformer](./transformer/README.md)

- Run [Consumer](./consumer/README.md)
  