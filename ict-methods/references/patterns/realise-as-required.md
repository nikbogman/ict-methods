# Realise as required

Strategies: field → workshop → lab

## Why?

In most cases, your stakeholders know exactly what they would like from the IT system/application you are developing. Understanding all the stakeholders' needs and wishes, and realising a solution that conforms to these where possible, can be a challenge. This pattern helps to structurally investigate, realise and test your solution based on the stakeholders' needs.

## How?

Developing an IT system that meets the stakeholders' demands, requires extensive investigation of what it is they actually need (Field). This is the basis for realising the system (Workshop). Mostly, an iterative approach (such as Agile) works best to loop over Field, Workshop and Lab, so that stakeholders can evaluate and give feedback on intermediate results (Lab). Based on the feedback from the stakeholders, the requirements can be adapted and further refined for a next iteration of Field, Workshop and Lab.

## When?

This pattern typically starts during the analysis phase and continues during the design and realisation/evaluation phases. It also works very well in an agile setting, and therefore the loops can be repeated resulting in a continuously improving IT system that fits the needs of the stakeholders more accurately with every iteration (sprint).

## Risks

As this pattern does not take available work (Library, Showroom) into account, you might not be aware of solutions or comparable products that are already available and could help you or inspire ideas.

Tip: In case your knowledge about the (solution) domain is lagging, consider to first start or integrate with a Library related method such as comparable product analysis.

Another risk is that stakeholders could have opposing needs or that they differ in the prioritisation of the requirements. By deciding who will be responsible for the requirements and their prioritisation (called the Product Owner in Agile-scrum) at the end of the day before you begin, you can prevent long discussions or having to constantly change the requirements depending on who you are talking with.

## Examples from practice

### An app to inform concert visitors

You are asked to develop an app for an upcoming concert to inform visitors about the programme, guiding them through the areas of the concert, supporting them in making decisions about which stage to go, etc.

You perform a stakeholder analysis (Field), and conduct interviews with the most important stakeholders (Field). You define and prioritise the requirements as user stories (Workshop) and develop the app in a number of sprints. At the end of each sprint, you test against the requirements with system tests (Lab) and do usability testing (Lab). Also, you define the priorities and if needed, update the user stories together with the stakeholders (Field/Workshop).

1. Field — What are the needs of the stakeholders?
2. Workshop — Define user stories. What is the priority of the user stories for the stakeholders?
3. Workshop — Realise the user story as an artefact
4. Lab — Test the artefact. What are the results from system- and usability tests?

### Define a new website UX

A company wants to change their branding and their websites to be fully redesigned as well. You are asked to define the new UX of the websites. You assemble a focus group to define and clarify what is important in terms of UX for this company and their users (Field). Based on this input, you create a paper prototype (Workshop). After that, you select a small representative group of users and ask them to go through your prototype whilst thinking out loud (Lab).

1. Field — What are important UX aspects for the stakeholders?
2. Workshop — Create a paper prototype
3. Lab — How do users experience the usability of the prototype (when talking out loud)?

### Psy-bot

You are asked to develop a chatbot using RAG (retrieval augmented generation) that can support psychological consults for youngsters (12–14 years) struggling with self-regulation. To understand their needs, you first conduct interviews (Field) and observations (Field) with youngsters to learn how they currently deal with self-regulation challenges. Based on this input, you create a first prototype of the chatbot (Workshop). Once early iterations are available, you apply Silicon Sampling (Workshop) to explore utopian and dystopian scenarios of how the chatbot could affect youngsters' autonomy, well-being, and relationships. The insights from these ethical explorations guide new design iterations. During these iterations, you conduct usability tests (Lab) to check to what extent the ethical scenarios are recognizable in practice and whether users experience them positively or negatively. Findings from the tests lead to further refinements of the prototype.

1. Field — What are the needs and experiences of the youngsters?
2. Workshop — Build a prototype of the chatbot.
3. Workshop — Use Silicon Sampling to explore utopian and dystopian scenarios.
4. Workshop — Adapt the prototype based on ethical reflections.
5. Lab — Usability tests: are ethical scenarios visible and acceptable in practice?
