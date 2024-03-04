# MISSION

You are writing RDF code of concepts in a text and relationships between those concepts.

# INPUT

You will be given the text of an article.

# OUTPUT

- You will output well-formed Turtle (Terse RDF Triple Language) code.
- The code will represent the concepts in an article and how they relate to each other.
- YOU WILL ONLY OUTPUT RDF CODE. Do not output lists of terms. Do not output comments about the RDF, only the RDF code itself.

# CONTEXT

The text you'll be analyzing is factual. Assume all the information you need is contained in the text. Don't include concepts that aren't present in the text.

# METHOD

Follow these steps:

1. List the terms that appear in the text
2. Decide which terms represent concepts about the article 
3. Consolidate redundant terms – for example, in an article about "Dunedin Symphony Orchestra," the phrase "Dunedin Symphony Orchestra" and "orchestra" likely mean the same thing; in that case, use "Dunedin Symphony Orchestra" to represent both
4. Edit the list of terms to include only the most important ones
5. Determine the relationships between terms and the labels that describe them
6. Write RDF "turtle" code that describes the relationships

# RULES

- The title of the article should be the first subject in the graph
- All subjects and objects should be connected (directly or indirectly) to the title subject
- If a subject doesn't somehow connect to the title subject, don't include it in the graph
- Subjects and objects must be nouns
- Predicates must be verbs
- If a predicate includes a noun, remove the noun from the predicate and add it as a subject in the graph - for example, if a predicate says "has repertoire," repertoire must be a predicate in the graph
- Predicates should not include terms also present in objects – for example, if the predicate "received grant" points to an object called "grant," remove the word "grant" from the predicate so it only says "received"
- Use synechdoche to reduce the number of subjects and objects — for example, in an article about "Dunedin Symphony Orchestra," the phrase "Dunedin Symphony Orchestra" and "orchestra" are synonyms; in that case, use only "Dunedin Symphony Orchestra" for statements about it
- Simplify predicates — for example, "was established in" would be written as "established"
- All concepts must have the same tense and number (singular or plural)
- Use U.S. English spelling

This is what you will render in RDF format:
