---
layout: default
---


## Neo4J Overview: Features & Use Cases

### Introduction
Neo4j is an open-source NoSQL graph database developed using Java and Scala. Graph databases focus on relationships between nodes of data, making the connections between the nodes the primary focus rather than the data itself. This allows for the discovery and exploration of patterns and connections within the data that would be difficult using a traditional relational database.

### Features
Neo4j offers:

- 	Flexible schema
- 	ACID transactions
- 	Constant, real-time performance
- 	Scale & Performance
- 	Cypher Query Language
- 	Cloud-ready architecture
- 	Data import tools
- 	Hot backups
- 	In-memory page cache (Enterprise Edition)
- 	Elastic Scalability (Enterprise Edition)

Graph databases such as neo4j are built on a Property Graph Model that is similar in many ways to an object model or entity relationship diagram (ERD).  The graph is made from nodes (entities) which hold any number of attributes stored as key-value pairs.  These nodes are connected to each other using directional relationships which may also have properties.  These relationship properties are generally quantitative, for example weight, cost, distance, etc.  Relationships must always have a start and end node.  When deleting any node, all it’s relationships are also deleted.

{% include figure.html
    src = "/images/ex-property-graph-model.png"
    alt="Example of property-graph model."
    caption="Property Graph Model, example from [Neo4j docs](https://neo4j.com/developer/graph-database/#property-graph)"
%}

### Use Cases
Graph databases, such as Neo4j are ideal for use cases where the relationships and connections between pieces of data are complex and a main focus of the analysis.  Examples of common use cases include graph-based searches, social networks, recommendation engines, fraud detection, and network and IT operations. In all of these use cases, how the data is connected is crucial to the analysis.

#### Investigative journalism
One of the more interesting use cases to me was investigative journalism.  Journalists have found a great deal of benefit in using graph databases for analysis of leaked data.  One of the key examples of this is found in the International Consortium of Investigative Journalists (ICIJ) analysis of the HSBC fraud (Boland-Rudder).  The ICIJ received leaked data on over 100,000 Swiss bank accounts, contained in a dataset composed of more than 60,000 files.  To identify the connections between the accounts, they used neo4j to build a database of over 270,000 nodes with more than 400,000 relationships.  This allowed them to link accounts where owners used code names for obfuscation over multiple layers of ownership.  

A smaller and more accessible example is found in a GraphGist analyzing the Panama Papers Dataset of the President of Azerbaijan, Ilham Aliyev and his family (Hunger).  The article walks through an analysis of a small set of this data as a tutorial on using a graph database for investigative journalism.  It illustrates how the data can be built and queried using neo4j.

{% include figure.html
    src = "/images/ex-fraud-pan-papers.png"
    alt="Example data: family member & organizational relationships graph"
    caption="Sample Data:  Relationships between family members & organizations"
%}

{% include figure.html
    src = "/images/ex-fraud-pan-papers-family.png"
    alt="Example data: family member relationships graph"
    caption="Sample Data:  Relationships between family members"
%}

By combining the data from the two datasets, you can see a fuller picture of how the organizational members are interconnected through the family relationships.

{% include figure.html
    src = "/images/ex-fraud-pan-papers-combined.png"
    alt="Example data: combined relationships graph"
    caption="Sample Data: Combination of organizational and family relationships"
%}

While this is a small and fairly simple example, the same type of analysis can be used and applied to many different use cases and scenarios.  As the dataset becomes larger, the connections are not as obvious without the assistance of the data graph and query support.  

#### Fraud detection
A similar use case is for fraud detection. A general example is presented in another GraphGist on bank fraud (Bastani). Here relationships between accounts are identified through common data such as an address, phone number, or SSN.  Once one account has been identified as being involved in fraudulent transactions, other connected accounts can then also be marked for fraud investigation as shown in the diagram below.

{% include figure.html
    src = "/images/ex-bank-fraud.png"
    alt="Example bank fraud model"
    caption="Bank Fraud Model"
%}



### References

- Bastani, K. (n.d.). GraphGist: Bank Fraud. Retrieved September 10, 2016, from Neo4j: [https://neo4j.com/graphgist/9d627127-003b-411a-b3ce-f8d3970c2afa]()
- Boland-Rudder, H. (2015, October 19). How the ICIJ Unraveled HSBC Fraud Using Neo4j & Linkurious. Retrieved September 10, 2016, from neo4j: [https://neo4j.com/blog/icij-hsbc-fraud-neo4j-linkurious/]()
- Haddou, L. (n.d.). Exploring networks with graph databases: A journalists' introduction to Neo4j. Retrieved Septemeber 10, 2016, from [http://leilahaddou.github.io/neo4j-tutorial.html]()
- Hunger, M. (n.d.). GraphGist: The PanamaPapers - Example Dataset President of Azerbaijan. Retrieved September 10, 2016, from neo4j: [https://neo4j.com/graphgist/b0502991-9a6e-4404-896a-a80a14098e98]()
- Neo4j. (n.d.). Retrieved September 10, 2016, from Neo4j: [https://neo4j.com/]()
