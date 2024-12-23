# Graph Query Lanaguage: The ISO standard for Graphs has arrived

https://www.theregister.com/2024/04/24/gql_iso_recognition/

https://www.theregister.com/2023/03/10/great_graph_debate_friday/

https://finance.yahoo.com/news/nebulagraph-enterprise-v5-0-first-140000670.html


The Graph Query Language (GQL) is an ISO standard specifically designed for querying property graphs. Officially published as ISO/IEC 39075:2024, GQL is the first new database language standard since SQL¹².

GQL provides a declarative approach to managing and querying property graphs, which are a type of graph where nodes (vertices) and edges (relationships) can have associated properties (key-value pairs). This makes it particularly powerful for complex data structures and relationships²³.

Key features of GQL include:
- **Creation and management** of property graphs.
- **CRUD operations** (Create, Read, Update, Delete) on nodes and edges.
- **Advanced querying capabilities** for traversing and analyzing graph data⁴.

This standard aims to unify and standardize the way property graphs are handled, much like SQL did for relational databases².

Is there something specific you would like to know about GQL or its applications?

Source: Conversation with Copilot, 10/1/2024
(1) Graph Query Language GQL. https://www.gqlstandards.org/.
(2) Graph Query Language - Wikipedia. https://en.wikipedia.org/wiki/Graph_Query_Language.
(3) The Rise of GQL: A New ISO Standard in Graph Query Language - TigerGraph. https://www.tigergraph.com/blogs/gsql/the-rise-of-gql-a-new-iso-standard-in-graph-query-language/.
(4) Understanding GQL: A Comprehensive Overview of the Standard Graph Query .... https://www.nebula-graph.io/posts/An_Comprehensive_Overview_of_the_Standard_Graph_Query_Language.
(5) Property Graph Standards Update - July 2020 - JCC 
Consulting. http://www.jcc.com/resources/jcc-blogs-menu/blog-database-dreams/122-property-graph-standards-update-july-2020.
(6) undefined. https://jtc1info.org/slug/gql-database-language/.

## The Databases

 Here are some databases that currently support or are planning to support the GQL standard:

1. **Neo4j**: Known for its Cypher query language, Neo4j is aligning its support with GQL¹⁴.
2. **Amazon Neptune**: This graph database service by AWS is also moving towards GQL compatibility¹⁴.
3. **TigerGraph**: TigerGraph's GSQL is another example of a graph query language that is converging towards GQL³.
4. **NebulaGraph**: NebulaGraph Enterprise v5.0 offers native GQL support⁵.

These databases are part of a broader movement to standardize graph database queries, making it easier for users to work with graph data across different platforms.


Source: Conversation with Copilot, 10/1/2024
(1) GQL: The ISO standard for graphs has arrived | AWS Database Blog. https://aws.amazon.com/blogs/database/gql-the-iso-standard-for-graphs-has-arrived/.
(2) ISO GQL: A Defining Moment in Database Innovation - Neo4j Graph Data .... https://neo4j.com/blog/gql-international-standard/.
(3) The Rise of GQL: A New ISO Standard in Graph Query Language - TigerGraph. https://www.tigergraph.com/blogs/gsql/the-rise-of-gql-a-new-iso-standard-in-graph-query-language/.
(4) Beyond a Query Language: How GQL is Shaping the Future of Graph Databases. https://www.nebula-graph.io/posts/How_GQL_is_Shaping_the_Future_of_Graph_Databases.
(5) Graph Query Language GQL. https://www.gqlstandards.org/home.
(6) undefined. https://jtc1info.org/slug/gql-database-language/.

The Graph Query Language (GQL) is an ISO standard specifically designed for querying property graphs. Officially published as ISO/IEC 39075:2024, GQL is the first new database language standard since SQL¹².

GQL provides a declarative approach to managing and querying property graphs, which are a type of graph where nodes (vertices) and edges (relationships) can have associated properties (key-value pairs). This makes it particularly powerful for complex data structures and relationships²³.

Key features of GQL include:
- **Creation and management** of property graphs.
- **CRUD operations** (Create, Read, Update, Delete) on nodes and edges.
- **Advanced querying capabilities** for traversing and analyzing graph data⁴.

This standard aims to unify and standardize the way property graphs are handled, much like SQL did for relational databases².

Is there something specific you would like to know about GQL or its applications?

Source: Conversation with Copilot, 10/1/2024
(1) Graph Query Language GQL. https://www.gqlstandards.org/.
(2) Graph Query Language - Wikipedia. https://en.wikipedia.org/wiki/Graph_Query_Language.
(3) The Rise of GQL: A New ISO Standard in Graph Query Language - TigerGraph. https://www.tigergraph.com/blogs/gsql/the-rise-of-gql-a-new-iso-standard-in-graph-query-language/.
(4) Understanding GQL: A Comprehensive Overview of the Standard Graph Query .... https://www.nebula-graph.io/posts/An_Comprehensive_Overview_of_the_Standard_Graph_Query_Language.
(5) Property Graph Standards Update - July 2020 - JCC Consulting. http://www.jcc.com/resources/jcc-blogs-menu/blog-database-dreams/122-property-graph-standards-update-july-2020.
(6) undefined. https://jtc1info.org/slug/gql-database-language/.

## Examples

https://www.nebula-graph.io/posts/An_Comprehensive_Overview_of_the_Standard_Graph_Query_Language

Here are some examples of how you can create and manage property graphs using GQL:

### Creating a Graph
To create a new graph, you can define the graph schema and then instantiate it. For example:

```gql
CREATE GRAPH TYPE socialNetworkSchema (
  Person (name STRING, age INT),
  Friend (since DATE)
);

CREATE GRAPH socialNetwork OF TYPE socialNetworkSchema;
```

### Adding Nodes and Edges
You can add nodes (vertices) and edges (relationships) to the graph:

```gql
INSERT INTO socialNetwork {
  (p1:Person {name: 'Alice', age: 30}),
  (p2:Person {name: 'Bob', age: 25}),
  (p1)-[:Friend {since: DATE '2020-01-01'}]->(p2)
};
```

### Querying the Graph
To query the graph, you can use pattern matching to find specific nodes and relationships:

```gql
MATCH (p:Person)-[f:Friend]->(q:Person)
WHERE p.name = 'Alice'
RETURN p, f, q;
```

### Updating Properties
You can update properties of nodes and edges:

```gql
MATCH (p:Person)
WHERE p.name = 'Alice'
SET p.age = 31;
```

### Deleting Nodes and Edges
To delete nodes and edges, you can use the `DETACH DELETE` command:

```gql
MATCH (p:Person)-[f:Friend]->(q:Person)
WHERE p.name = 'Alice' AND q.name = 'Bob'
DETACH DELETE p, f, q;
```

These examples illustrate some of the basic operations you can perform with GQL to manage property graphs⁶⁵. If you have any specific scenarios or more detailed queries, feel free to ask!

Source: Conversation with Copilot, 10/1/2024
(1) Understanding GQL: A Comprehensive Overview of the Standard Graph Query .... https://www.nebula-graph.io/posts/An_Comprehensive_Overview_of_the_Standard_Graph_Query_Language.
(2) Property Graph Standards Update - July 2020 - JCC Consulting. http://www.jcc.com/resources/jcc-blogs-menu/blog-database-dreams/122-property-graph-standards-update-july-2020.
(3) Graph Query Language - Wikipedia. https://en.wikipedia.org/wiki/Graph_Query_Language.
(4) GQL - initiating an industry standard property graph query language. https://db-engines.com/en/blog_post/78.
(5) Information technology — Database languages — GQL - ISO. https://www.iso.org/standard/76120.html.
(6) [2211.10962] PG-Schema: Schemas for Property Graphs - arXiv.org. https://arxiv.org/abs/2211.10962.

## GQL Relevance in the age of Generative AI

The GQL standard remains highly relevant and useful even in the age of generative AI and large language models (LLMs). Here are a few reasons why:

### Enhanced Data Management
- **Structured Data Handling**: GQL excels at managing complex, interconnected data structures, which is crucial for applications that require detailed data relationships, such as social networks, recommendation systems, and knowledge graphs.
- **Efficient Queries**: GQL's ability to perform complex queries efficiently can complement the unstructured data processing capabilities of LLMs, providing a robust backend for AI applications.

### Integration with AI
- **Knowledge Graphs**: GQL can be used to build and query knowledge graphs, which are essential for enhancing the contextual understanding of LLMs. These graphs can store vast amounts of structured information that LLMs can leverage to improve their responses.
- **Data Enrichment**: By integrating GQL with AI models, you can enrich the data stored in property graphs with insights derived from AI, leading to more intelligent and context-aware applications.

### Real-World Applications
- **Recommendation Systems**: Combining GQL with AI can enhance recommendation systems by leveraging both structured graph data and unstructured user behavior data.
- **Fraud Detection**: In financial services, GQL can help map out complex transaction networks, while AI can analyze patterns to detect fraudulent activities.

### Future-Proofing
- **Standardization**: As an ISO standard, GQL provides a consistent and reliable way to manage graph data, ensuring compatibility and interoperability across different systems and platforms.
- **Scalability**: GQL's design allows it to scale with the growing complexity and size of data, making it a future-proof choice for data management.

In summary, GQL and generative AI/LLMs can complement each other, with GQL providing a structured, efficient way to manage and query data, and AI models offering advanced data processing and analysis capabilities. This synergy can lead to more powerful and intelligent applications.

## Relevant for Developing AI Agents

GQL can be quite relevant in the development of AI agents, particularly in the following ways:

### Knowledge Representation
- **Structured Knowledge**: AI agents often need to access and manipulate structured knowledge. GQL allows for the creation and querying of knowledge graphs, which can represent complex relationships and hierarchies in a way that is easily accessible to AI agents.

### Data Integration
- **Combining Data Sources**: AI agents frequently need to integrate data from multiple sources. GQL can help by providing a unified way to query and manage this data, ensuring that the AI agent has access to comprehensive and up-to-date information.

### Contextual Understanding
- **Enhanced Context**: By leveraging property graphs, AI agents can gain a deeper understanding of the context in which they operate. This can improve decision-making and the generation of more relevant responses.

### Dynamic Querying
- **Real-Time Data Access**: AI agents can use GQL to perform real-time queries on dynamic data sets, allowing them to adapt to new information quickly and efficiently.

### Use Cases
- **Personal Assistants**: AI personal assistants can use GQL to manage user preferences, schedules, and relationships, providing more personalized and context-aware assistance.
- **Recommendation Systems**: AI agents in recommendation systems can use GQL to analyze user behavior and preferences, enhancing the accuracy and relevance of recommendations.
- **Fraud Detection**: In financial services, AI agents can use GQL to map out transaction networks and detect anomalies, improving fraud detection capabilities.

### Example
Imagine an AI agent designed to assist with project management. Using GQL, the agent can query a property graph to understand the relationships between tasks, team members, and deadlines. This allows the agent to provide more accurate updates, identify potential bottlenecks, and suggest optimizations.

In summary, GQL provides a robust framework for managing and querying the structured data that AI agents rely on, enhancing their capabilities and effectiveness. 

## Complement's LangGraph?

GQL (Graph Query Language) can indeed complement LangGraph in developing AI agents. Here's how:

1. **Data Management**: GQL is excellent for querying and managing graph data. This capability can be leveraged within LangGraph to efficiently handle and manipulate the complex data structures that AI agents often need to work with.

2. **Enhanced Querying**: LangGraph, which is designed for building stateful, multi-actor applications with LLMs (Large Language Models), can benefit from GQL's powerful querying capabilities. This allows for more sophisticated data retrieval and manipulation, which is crucial for developing advanced AI agents⁶.

3. **Integration**: LangGraph's framework supports the integration of various tools and data sources. By incorporating GQL, developers can create more dynamic and responsive AI agents that can query and process graph data in real-time⁹.

4. **Complex Workflows**: Both GQL and LangGraph are well-suited for handling complex workflows. GQL can manage the underlying data relationships, while LangGraph can orchestrate the flow of information and decision-making processes within the AI agent⁶⁹.

Combining these two technologies can lead to the development of more robust and intelligent AI agents capable of handling intricate tasks and providing personalized experiences.

Would you like to explore a specific use case or example of how this integration might work?

Source: Conversation with Copilot, 10/1/2024
(1) langchain-ai/langgraph: Build resilient language agents as graphs. - GitHub. https://github.com/langchain-ai/langgraph.
(2) LangGraph - LangChain. https://www.langchain.com/langgraph.
(3) Using LangGraph to build better AI Agents - Geeky Gadgets. https://www.geeky-gadgets.com/using-langgraph-to-build-ai-agents/.
(4) Develop a Master AI Agent With LangGraph in Python. https://thenewstack.io/develop-a-master-ai-agent-with-langgraph-in-python/.
(5) How to build AI agents using LangGraph Llama 3 and Groq. https://www.geeky-gadgets.com/how-to-build-ai-agents/.
(6) AI Agents in LangGraph. https://www.deeplearning.ai/short-courses/ai-agents-in-langgraph/.
(7) ksm26/AI-Agents-in-LangGraph - GitHub. https://github.com/ksm26/AI-Agents-in-LangGraph.
(8) langgraph/examples/multi_agent/multi-agent-collaboration.ipynb at main .... https://github.com/langchain-ai/langgraph/blob/main/examples/multi_agent/multi-agent-collaboration.ipynb.
(9) Building Complex Multi-Agent Teams and Setups with LangGraph. https://blog.finxter.com/building-complex-multi-agent-teams-and-setups-with-langgraph/.
(10) LangGraph Tutorial: What Is LangGraph and How to Use It?. https://www.datacamp.com/tutorial/langgraph-tutorial.
(11) langgraph · PyPI. https://pypi.org/project/langgraph/.
(12) langgraph/README.md at main · langchain-ai/langgraph - GitHub. https://github.com/langchain-ai/langgraph/blob/main/README.md.





