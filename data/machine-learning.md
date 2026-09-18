# Machine Learning

Machine Learning (ML) software is a software system with one or more components that learn from data. This entails engineering a pipeline for the collection and pre-processing of data, the training of an ML model, the deployment of the trained model to perform inference and the software engineering of the encompassing software system that sends new input data to the model to get answers.

ML projects are different from traditional rule-based software engineering. Eight challenges for engineering machine learning applications have been identified:

1. Data requirements engineering including data visualizations
2. ML components are more difficult to handle as distinct modules
3. Design of the ML component through algorithm selection and tuning
4. Break up the ML development in increments
5. Data and model management for the current and future projects
6. Find ML models that can be reused for your application
7. Validation of ML applications in absence of a specification to test against
8. Explainability of ML models is needed for debugging

## Data Analytics does not fit ML projects

There is a research method called Data analytics (in the Lab strategy). This does not reflect the way of working in ML projects, where Data Analytics is not a method to answer one question but a method to fulfil the main goal of the project. For ML projects, the Data Analytics method should be divided into several smaller steps, each becoming a method of its own. In other words, the Data Analytics (or more appropriately, ML engineering) process should be treated the same way the software engineering process is treated in the DOT framework.

The high-level steps of an ML project (derived from CRISP-DM) replace the single Data Analytics method with several separate methods:

- **Data collection.** Based on the model requirements (what type of data?) and the business understanding (which content should be in the data?), collect the data that is needed to train the ML model.
- **Exploratory data analysis (Field).** Instead of requirements you have input data. Instead of interviewing users to collect requirements, you explore the given data to learn what you can do with it.
- **Data preparation.** Once you understand the data, transform it so that it can be used for training an ML model.
- **Data quality check (Lab).** Next to testing the software you should also test the data — wrong input data produces wrong answers from the model.
- **ML model training.** The way to approach the training of ML models is very specific; algorithm selection and hyperparameter tuning are part of it.
- **Model validation (Lab).** Next to testing software and data, you also need to test the trained model.
- **Model evaluation (Lab).** Translate the ML model results to communicate and validate them with end users (e.g. through data visualization).

Data collection, data preparation and ML model training are engineering steps that do not qualify as ICT research methods. The other four (exploratory data analysis, data quality check, model validation, model evaluation) require a "card" of their own for ML projects, but might also be useful in other types of projects.

## Applying existing methods to ML projects

For brief discussions of how the standard research methods apply to ML projects, see:

- Library methods for machine learning
- Field methods for machine learning
- Workshop methods for machine learning
- Lab methods for machine learning
- Showroom methods for machine learning
