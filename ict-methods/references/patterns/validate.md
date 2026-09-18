# Validate

Strategies: workshop → lab / showroom

## Why?

The validation pattern enables you to check whether your ideas, assumptions, designs et cetera really lead to the results you were hoping for. In this respect, the validation patterns help you to monitor the quality of your project. Typically, this involves answering two questions: (a) to what extent do project outcomes (e.g., prototypes) solve the problem that initiated the project? and (b) to what extent are project processes and outcomes examples of good professionalism?

## How?

The type of test that you will perform depends on the type of product and the quality criteria that you want to know more about. The starting point is the artefact created (outcome of the Workshop activity). To get an understanding of whether your artefact satisfies the needs of the stakeholders, you can use Lab methods such as system testing, usability testing or another non-functional test such as performance testing. To get an understanding of the professionalism of your artefact, you can use Showroom methods such as a review by experts, or automatic tools that can give an indication of the quality of your product (typically for software code).

Remember that most tests include others such as stakeholders or experts and therefore communication skills are important as you want to involve them and support them in order to get the results that can help you.

## When?

Even though this pattern can be used during all project phases, it relies on the fact that you have collected some (first) results from the Workshop strategy such as a (paper) prototype, design documents, etc.

Also note that when these results are still 'sketchy' and 'paper prototype(-ish)' this will have an impact on the methods you can use to execute the validation pattern when your workshop products become more tangible.

## Risks

Especially when users are involved, there is not always a clear or direct relationship between what you want to validate and how this can be measured or tested. This demands some extra research, commonly including more Library methods, to refine your test plan.

When using Showroom methods during the Validation loop, always clarify what exactly you want to validate. If your objectives for Showroom methods are not set out clearly, you might just have proven that you did 'some work' but not that you have created added value. Showing added value to the project should always be an important aspect of the Showroom strategy.

## Examples from practice

### A progressive web application

You have worked hard to develop a progressive web application and you have already used Lab methods such as unit testing to verify the correctness of the methods and parts of the application. Also, you used Showroom methods such as static program analysis (e.g., with SonarQube) to verify the quality of your code.

Now that you have realised a first version of the application, it needs to be validated against the requirements which resulted from earlier research. You conduct system testing and performance testing (performance was important to the customer). Also, you pitch your application and results to both the stakeholders and to some senior architects from the company and use their feedback to improve your application.

1. Workshop — Develop a first version of the application
2. Showroom — Verify code quality
3. Lab — Test your application
4. Showroom — Pitch your application to stakeholders and senior architects

### Online booking platform

For an online ticket booking platform you are building an application that uses caching to handle large amounts of ticket sales within a very short time. Building the application involved a lot of prototyping, but during the last iterations you have included several typical software engineering tests such as unit tests, A/B testing and code reviews from Lab and Workshop.

As the project reaches the final phase you decide to add a benchmark test (Showroom) in which you compare your new application with the existing application. This way, you are able to show that your application scores 20 to 30% better than the existing application on the top three requirements of your stakeholder.

1. Workshop — Build prototypes and perform code reviews
2. Lab — How can I monitor the quality of the application I'm building?
3. Workshop — Build prototypes and perform code reviews
4. Showroom — How can I show the quality of my solution compared to another?

### A video game for teens

You have been working on a video game in which the objective is to make teens more aware of the impact of peer pressure on starting to use drugs. You perform play tests including a survey (Lab) to validate whether players understand the game. To find a way to measure if the teens' gameplay is actually influenced by peer pressure, you interview an expert (Library) and study relevant literature (Library). The outcome is to add a data analysis (Lab) to your play test. To show that your method for measuring peer pressure is valid, you compare with existing guidelines in a Guideline conformity analysis (Showroom).

1. Workshop — Develop a video game
2. Lab — Do players understand the game?
3. Library — How to measure the impact of the game?
4. Lab — Measure the impact of the game
5. Showroom — How does the method used compare to existing guidelines?

### A serious game for a marketing campaign

You designed a serious game to promote new chocolate paste flavors to children. Earlier, you did a focus group with kids, parents, and teachers (field) and studied literature on ethics in commercials (library). These results gave you guidelines for what is and isn't acceptable when advertising to children. With a first prototype ready, you do an ethical check (showroom) with company stakeholders to see if the game follows these guidelines. Then, you run a usability test (lab) with children to check if ethical problems appear in practice, like the game being too persuasive or unhealthy. Finally, an ethics expert does a heuristic evaluation (showroom) to make sure the game meets ethical standards. All these insights help you improve the game and keep it ethically sound.

1. Workshop — Build the first prototype of the game
2. Showroom — Ethical check with company stakeholders
3. Lab — Usability test with children
4. Showroom — Heuristic evaluation by an ethics expert
