# Knowledge Graph Triples

Knowledge graph triples (also known as semantic triples) are the fundamental building blocks of knowledge graphs. They represent individual knowledge claims by breaking information down into three distinct parts: a **Subject**, a **Predicate** and an **Object**. Put another way, triples describe a relationship between two nodes on the graph. 

## Structure

- **Subject**: The entity (node) being described.
- **Predicate**: The relationship linking the **Subject** to the **Object**.
- **Object**: The target entity (node) that the **Subject** relates to.

## Inference

When multiple triples are linked together, new facts that aren’t explicitly stated can be inferred. For example, consider the following triples:

- John | is_father_of | Ben
- Ben | lives_in | New York 

Taken together with the general rule that fathers tend to live close to their children, we can infer from these two triples that John (probably) lives in New York, a fact not directly stated. 

## Standardization

Triples are the main knowledge structures used in RDF, the Resource Description Framework, a World Wide Web Consortium (W3C) standard designed to model, describe and exchange graph-based data across systems. W3C’s RDF standards provide the official framework for publishing, linking and exchanging triples on the web.

[Semantic Triple](https://en.wikipedia.org/wiki/Semantic_triple)

[RDF | Semantic Web Standards](https://www.w3.org/RDF/)
