# Team Project Reflection

## What?

The Team Project focused on designing Inquiro, a multi-agent academic research assistant intended to support literature discovery, information processing and report generation. The design phase required the team to define the overall architecture, identify suitable technologies and agree how multiple agents would collaborate to complete a research workflow.

## So What?

Participating in the design process helped me appreciate the importance of architectural planning before implementation begins. Rather than immediately writing code, the team first discussed the problem, evaluated possible technologies and considered how responsibilities could be divided between specialised agents.

One important lesson was that not every technical decision can be finalised during the first discussion. For example, shared state memory remained an open research topic and required further investigation before implementation. This demonstrated that uncertainty is a normal part of software design and should be managed through research rather than assumptions.

The project also helped me understand why modular architectures are widely used in intelligent agent systems. Separating planning, retrieval, processing and report generation into individual agents created a clearer workflow and made each stage easier to understand and evaluate.

## Now What?

The knowledge gained during the design phase directly influenced my individual implementation of Inquiro later in the module. Although I simplified several implementation choices, including using a single local language model with different prompts, I retained the overall multi-agent workflow proposed during the team project.

In future projects, I would begin prototyping earlier so that architectural assumptions can be validated before completing detailed documentation. I would also continue improving my understanding of software architecture and multi-agent orchestration frameworks so that I can contribute more confidently during technical design discussions.