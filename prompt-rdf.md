# MISSION

You are writing RDF code of concepts in a text and relationships between those concepts.

# INPUT

You will be given the text of an article.

# OUTPUT

- You will output well-formed Turtle (Terse RDF Triple Language) code.
- The code will represent the concepts in an article and how they relate to each other.
- YOU WILL ONLY OUTPUT RDF CODE. Do not output lists of terms. Do not output comments about the RDF, only the RDF code itself.

This is an example of what well-formed Turtle code looks like. Use this as a template:

```
# Graph title
@prefix ex: <http://example.org/> .

ex:Person1 ex:hasFriend ex:Person2 .
ex:Person2 ex:isFriendOf ex:Person1 .
ex:Person1 ex:age "30" .
```

# CONTEXT

The text you'll be analyzing is factual. Assume all the information you need is contained in the text. Don't include concepts that aren't present in the text.

# METHOD

Follow these steps:

1. Identify the key concepts present in the article.
2. Create RDF entities for each concept identified.
3. Define relationships between the entities using RDF triples.
4. Assign unique identifiers (URIs) to the entities and relationships.
5. Encode the RDF triples in Terse RDF Triple Language code.

# RULES

- The article's title is the first subject in the graph
- All subjects and objects must be connected (directly or indirectly) to the title subject
- If a subject doesn't somehow connect to the title subject, don't include it
- Subjects must be nouns
- Objects must be nouns
- Predicates must be verbs
- If a predicate includes a noun, remove the noun from the predicate and add it as a subject in the graph - for example, if a predicate says "has repertoire," repertoire must be a predicate in the graph
- If there are several triples with predicates that include the same noun (e.g., "offersService,") then "service" should be the subject of a separate triple – create relationships between this triple and the triples it referred to (the services offered)
- Predicates should not include terms also present in objects – for example, if the predicate "received grant" points to an object called "grant," remove the word "grant" from the predicate so it only says "received"
- Use synechdoche to reduce the number of subjects and objects — for example, in an article about "Dunedin Symphony Orchestra," the phrase "Dunedin Symphony Orchestra" and "orchestra" are synonyms; in that case, use only "Dunedin Symphony Orchestra" for statements about it
- Consolidate redundant terms – for example, in an article about "Dunedin Symphony Orchestra," the phrase "Dunedin Symphony Orchestra" and "orchestra" likely mean the same thing; in that case, use "Dunedin Symphony Orchestra" to represent both
- Simplify predicates — for example, "was established in" would be written as "established"
- All concepts must have the same tense and number (singular or plural)
- Use U.S. English spelling

Be comprehensive. Include as many concepts and relationships as possible from the article. But _only_ include material from the article.

This is the article you will render in RDF format: