# Unit 8 Activity – Constituency-Based Parse Trees

## Activity Overview

This activity required me to create constituency-based parse trees for three English sentences. The purpose was to practise identifying the main grammatical constituents within a sentence, including noun phrases (NP), verb phrases (VP) and prepositional phrases (PP).

The activity also demonstrated how constituency parsing provides a structured representation of natural language and highlighted that some sentences can have more than one valid interpretation.

---

# Sentence 1

**The government raised interest rates.**

```text
(S
  (NP
    (DT The)
    (NN government))
  (VP
    (VBD raised)
    (NP
      (NN interest)
      (NNS rates))))
```

### Explanation

The sentence consists of:

- **Subject (NP):** *The government*
- **Verb (VBD):** *raised*
- **Object (NP):** *interest rates*

The parse tree clearly separates the subject noun phrase from the verb phrase, illustrating a straightforward sentence structure.

---

# Sentence 2

**The internet gives everyone a voice.**

```text
(S
  (NP
    (DT The)
    (NN internet))
  (VP
    (VBZ gives)
    (NP
      (NN everyone))
    (NP
      (DT a)
      (NN voice))))
```

### Explanation

This sentence contains:

- **Subject (NP):** *The internet*
- **Verb (VBZ):** *gives*
- **Indirect Object (NP):** *everyone*
- **Direct Object (NP):** *a voice*

Unlike the first sentence, the verb takes two complements, demonstrating how constituency trees represent more complex sentence structures.

---

# Sentence 3

**The man saw the dog with the telescope.**

This sentence is structurally ambiguous because the prepositional phrase **"with the telescope"** can modify either the verb phrase or the noun phrase.

---

## Interpretation 1 – The man used the telescope

```text
(S
  (NP
    (DT The)
    (NN man))
  (VP
    (VBD saw)
    (NP
      (DT the)
      (NN dog))
    (PP
      (IN with)
      (NP
        (DT the)
        (NN telescope)))))
```

### Meaning

The telescope describes **how the man saw the dog**.

---

## Interpretation 2 – The dog had the telescope

```text
(S
  (NP
    (DT The)
    (NN man))
  (VP
    (VBD saw)
    (NP
      (NP
        (DT the)
        (NN dog))
      (PP
        (IN with)
        (NP
          (DT the)
          (NN telescope))))))
```

### Meaning

The telescope describes **the dog**, rather than the action of seeing.

---

# Learning from the Activity

This exercise demonstrated that constituency parsing is more than identifying grammatical components. It provides a structured representation of sentence syntax that enables Natural Language Processing systems to analyse language systematically.

The third example was particularly valuable because it illustrated structural ambiguity. Although the sentence contains exactly the same words, different parse trees produce different meanings depending on where the prepositional phrase is attached.

Understanding these ambiguities is important in many NLP applications, including information extraction, question answering, machine translation and intelligent agent communication, where interpreting the intended meaning correctly is essential.

Overall, this activity strengthened my understanding of constituency-based parsing and demonstrated why syntactic analysis remains an important component of Natural Language Processing.