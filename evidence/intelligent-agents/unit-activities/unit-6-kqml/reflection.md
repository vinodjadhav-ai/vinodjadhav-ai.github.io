# Unit 6 Activity Reflection

## What?

This activity required me to create a simple dialogue between two software agents using KQML performatives and KIF-style knowledge representation. Alice acted as a procurement agent and Bob acted as a warehouse stock-control agent. The dialogue involved Alice requesting information about the availability of 50-inch televisions and the number of HDMI ports they provide.

Before this activity, I understood that agents could communicate with one another, but I had not considered how the structure and meaning of messages are represented. Creating the dialogue helped me understand how KQML defines the intention of a message, while KIF represents the actual knowledge being exchanged.

---

## So What?

This activity helped me connect the theoretical concepts introduced during Unit 6 with a practical example. I learned that successful communication between intelligent agents depends on more than simply exchanging information. Both agents must also share a common understanding of the concepts being used through an agreed ontology.

I also realised that there is a clear distinction between **what an agent wants to do** (for example, asking for information using the `ask-one` performative) and **the information itself** (represented using KIF expressions). Although modern AI systems often use APIs, JSON messages or shared state instead of KQML, the same communication principles still apply. Agents still need a clear message structure, shared terminology and agreed communication rules.

As someone who is still developing my understanding of intelligent agents, this activity made the topic much easier to understand because I could see how abstract concepts are applied in practice.

---

## Now What?

In future projects involving multiple agents, I would spend more time designing communication before writing any implementation code. I would clearly define the message formats, shared ontology and possible responses, including error conditions when information is unavailable or inconsistent.

This activity also helped me appreciate why communication standards remain important in modern multi-agent systems. While implementing my Inquiro project later in the module, I noticed similar principles when different agents exchanged information through the workflow. Although the implementation technology was different, the need for structured communication and shared understanding remained the same.

Overall, this activity strengthened my understanding of agent communication and increased my confidence in applying these concepts in future AI projects.