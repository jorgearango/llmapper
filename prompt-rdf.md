# MISSION

You are an expert creating an RDF knowledge graph from a list of concepts and relationships between them.

# INPUT

You will be given a list of concepts and a list of relationships between those concepts.

# OUTPUT

Use this as a template:

```
@prefix ex: <http://example.org/ns#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix rel: <http://example.org/relations#> .

ex:JohnDoe
    a foaf:Person ;
    foaf:name "John Doe" ;
    foaf:mbox <mailto:john.doe@example.com> ;
    ex:interest ex:Reading,
                ex:Hiking,
                ex:Photography ;
    rel:knows ex:JaneDoe .

ex:JaneDoe
    a foaf:Person ;
    foaf:name "Jane Doe" ;
    foaf:mbox <mailto:jane.doe@example.com> ;
    ex:interest ex:Painting,
                ex:Gardening .

ex:Reading
    a ex:Hobby ;
    rdfs:label "Reading" .

ex:Hiking
    a ex:Hobby ;
    rdfs:label "Hiking" .

ex:Photography
    a ex:Hobby ;
    rdfs:label "Photography" .

ex:Painting
    a ex:Hobby ;
    rdfs:label "Painting" .

ex:Gardening
    a ex:Hobby ;
    rdfs:label "Gardening" .

rel:knows
    a owl:ObjectProperty ;
    rdfs:label "knows" .
```


# CONTEXT

In the template above, JohnDoe is the subject, JaneDoe is the object, and knows is the predicate that joins them.

The text you'll be analyzing is factual. Assume all the information you need is contained in the text. Don't include concepts that aren't present in the text.


# METHOD

Follow these steps:

1. Decide what are the most important concepts in the article. The most important concepts are those that are central to the article. Ignore details.
2. Create RDF entities for each concept.
3. Define relationships between the entities using RDF triples.
4. Assign unique identifiers (URIs) to the entities and relationships.
5. Encode the RDF triples in Terse RDF Triple Language code.

# RULES

- You will output well-formed RDF code.
- The code will represent the concepts in an article and how they relate to each other.
- YOU WILL ONLY OUTPUT RDF CODE. Do not output lists of terms. Do not output comments about the RDF, only the RDF code itself.
- Do not include Markdown code block markup, including backticks
- Consolidate concepts that are likely to refer to the same thing by different names. For example, in a knowledge graph about "The Lord of the Rings," the concepts "J. R. R. Tolkien" and "Tolkien" likely refer to the same person. In that case, use only the more specific of the two. (In this case, "J. R. R. Tolkien".)
- Don't use camelCase. Instead, use normal notation with spacing between words and encode them in double quotes as in the template above.
- Don't use snake_case. Instead, use normal notation with spacing between words and encode them in double quotes as in the template above.
- Don't use kebab-case. Instead, use normal notation with spacing between words and encode them in double quotes as in the template above.
- Don't use PascalCase. Instead, use normal notation with spacing between words and encode them in double quotes as in the template above.
Instead, encode them in double quotes as in the template above.
- Don't include any lists in subjects or objects. If you encounter a subject or object with more than one noun, you *must* break them up into separate triples. For example, the following triple:

	"first series" "features" "Martin Landau, Barbara Bain, Barry Morse" .
	
	must be broken up into three separate triples, one for each item in the list:
	
	"first series" "features" "Martin Landau" .
	"first series" "features" "Barbara Bain" .
	"first series" "features" "Barry Morse" .
	
- Shorten long subjects and objects. For example, the following triple:
	
	ex:famousFor "shops selling uniforms and equipment for military and police officers" .
	
	must be rewritten like this:
	
	ex:famousFor "military/police shops" .

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

Be comprehensive. Include as many concepts and relationships as possible from the input. But _only_ include material from the input.

This is the article you will render in RDF format:
