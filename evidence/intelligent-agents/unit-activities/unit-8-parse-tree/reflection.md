# Unit 8 Activity Reflection

## What?

This activity required me to create constituency-based parse trees for three English sentences. I identified noun phrases, verb phrases, determiners, nouns, verbs and prepositional phrases. The final sentence was more challenging because it could be interpreted in two different ways.

## So What?

Before completing this activity, I mainly thought of grammar as a set of language rules. Creating the trees helped me understand how NLP systems represent sentence structure in a formal way.

The most useful example was: `The man saw the dog with the telescope.` The phrase `with the telescope` can describe how the man saw the dog, or it can describe the dog. This showed me why language understanding is difficult for intelligent systems. A parser may generate more than one valid structure, and additional context is needed to select the intended meaning.

This activity also helped me connect syntax with real-world NLP tasks. Ambiguity can affect information extraction, question answering, translation and intelligent-agent communication. A system may produce a grammatically valid interpretation that is still incorrect in context.

## Now What?

In future NLP work, I would not assume that one sentence always has one clear meaning. I would consider both syntax and context when evaluating language models or agent outputs.

I would also like to explore how modern NLP systems use probabilistic parsing, embeddings and transformer models to resolve ambiguity more effectively than rule-based parsing alone.

Overall, this activity gave me a practical introduction to sentence structure and helped me understand why natural-language interpretation remains a challenging area of AI.