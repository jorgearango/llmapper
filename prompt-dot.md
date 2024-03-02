You are creating concept maps using the DOT diagramming language. You will make a concept map of the ideas in a text using the DOT language. Only use the ideas in the text, do not add or remove. 

In the DOT language, graphs are built using the following format:

digraph {
    "a" -> "b"[label="x"];
}

where 

1. 'a' represents the subject. 'b' represents the object. 

In this form, 'a' and 'b' should always be nouns. They are called concepts. Keep the number of concepts to a minimum: 

- Keep concepts short; no more than two words for each unless the concept is a proper name. (E.g., the name of the painting "The Garden of Earthly Delights" is a proper name and should be kept intact.)
- If a concept appears both in plural form (e.g., 'elephants') and singlular form (e.g., 'elephant',) replace the plural with the singular. (E.g., change 'elephants' to 'elephant'.)
- Generalize: If one concept includes the phrase 'gray elephants' and another the word 'elephants', assume they are the same and select 'elephants' for both
- Concepts cannot contain verbs. If a concept includes a verb (e.g., 'temple hosts',) then 'temple' is the subject and 'hosts' is a predicate. In that case, focus on 'temple' as the concept.

2. 'x' represents the predicate. 'x' should be an action/verb that concept 'a' does to concept 'b'. This is called a label. Labels should always be a verb and not exceed more than two words. Keep labels short; no more than two words for each.

Using the DOT language, write code to generate a graph that expresses the relationship between the following concepts. Do not include any introductory text, only the DOT code that starts with 'digraph'. 

3. Only make concept pairs for the sentences in the text. Do not introduce or remove sentences.

4. Concept names and labels should always be enclosed in double quotes.

Each concept pair must include a label. The label must be a verb.

Don't include any comments in the code, especially comments indicating what kind of language this is.

Follow these steps:

1. List the terms that appear in the text
2. Edit the list of terms to include only the most important ones
3. Determine the relationships between terms and the labels that describe them

All concepts (e.g. banana) must be lowercase, except proper those that contain proper nouns (e.g., Smith, Johanson, England, Microsoft) must be capitalized.

Labels should only include verbs. Labels should be no more than two words long. Labels must be lowercase.

Don't include information about the article itself, only the subject it covers.

If a concept is an acronym for another concept, use the full version. For example, "ANN" is an acronym for "Artificial Neural Networks." In this case, don't use ANN; use "Artificial Neural Networks" to represent both.

Excepting the first concept pair, at least one concept in a pair must refer to a concept in another pair. This may require using synechdoche. For example, in a text about watercolor painting, the word 'medium' may be considered a synonym for 'watercolor.' In that case, use 'watercolor' for both. Another example: in an article about 'Sengazhuneer Amman Temple,' the noun 'temple' on its own likely refers to 'Sengazhuneer Amman Temple.' In such cases, prefer the more specific noun 'Sengazhuneer Amman Temple.'

If a concept pair has a label that is a noun and a concept that is a verb, swap that label and concept.

If a concept and a label are the same, eliminate that pair from the list.

If a concept has a label that points to the same concept, eliminate that pair from the list.

Concepts can't be verbs. If a concept is a verb, eliminate that pair from the list.

When rendering the final code, insert the following styling commands inside the diagraph statement:

graph [fontname = "Arial"];
node [fontname = "Arial"];
edge [fontname = "Arial"];
node [shape=box, style="rounded,filled", fillcolor="#EDEEFA", color=transparent];

These commands must come at the beginning of the diagraph statement, immediately after the first bracket.

This is the text you will convert to DOT language:
