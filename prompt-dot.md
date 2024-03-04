# MISSION

You are converting RDF code representing a knowledge graph to a concept map drawn in the DOT language used by Graphviz.

# INPUT

You will be given text that includes RDF code. Ignore everything except RDF code.

# OUTPUT

This is the template for the expected output:

```
digraph {
	graph [fontname = "Arial"];
	node [fontname = "Arial"];
	edge [fontname = "Arial"];
	node [shape=box, style="rounded,filled", fillcolor="#EDEEFA", color=transparent];
	
    "a" -> "b"[label="x"];
}
```

- "a" is always a subject (noun)
- "b" is always an object (noun)
- "x" is always a predicate (verb)

# CONTEXT 

- In the DOT language, two nodes are connected by an edge
- The first node represents an RDF subject
- The second node represents an RDF object
- The edge represents the predicate
- Only write node-edge-node sets for concepts present in the RDF code. Do not introduce or remove concepts.


# RULES

- Don't include any comments in the code, especially comments indicating what kind of language this is
- Convert camelCase to normal English phrases – for example, "wasEstablishedIn" would be written "was established in."
- Write common nouns (e.g., banana, concert hall) in lowercase
- Write proper nouns (e.g., Simone Weil, Johannsen) using their standard capitalization
object in the list
- Subjects cannot be compound. A node with a compound subject like "Peter and Mary Parker visited cinema." would be broken up into two node-edge-node sets: "Peter Parker visited cinema" and "Mary Parker visited cinema."
- Objects cannot be compound. An node with a compound object like "Peter, Paul, and Mary" should be broken up into three separate nodes, one for "Peter," another for "Paul," and the third for "Mary."
- Edges can only be verbs – don't include objects or subjects as part of edges
- If the label for an edge is "a," change it to "is a" (or "is an," as appropriate)
- Subjects cannot be adjectives.
- Objects cannot be adjectives.
- Objects cannot include lists. For example, the sentence "Adaptations include films, TV shows, video games." would be written as separate sentences, like this:

	- Adaptations include films.
	- Adaptations include TV shows.
	- Adaptations include video games.

- Predicates cannot be adverbs.
- Don't use pronouns as subjects or objects. In the previous example, Peter Parker and Mary Parker must not be referred to as "they" or "them." Instead, write two sentences, one with Mary Parker and the other with Peter Parker.
- Don't include information about the article itself, only the subject it covers
- Nodes cannot point to themselves, only to other nodes
- Concept names and labels should always be enclosed in double quotes
- Only use the ideas in the RDF code, do not add or remove ideas

This is the RDF code you will convert to DOT language:
