# Lab methods for machine learning

For Machine Learning projects, the existing Lab methods can be applied as follows:

- **A/B testing.** A good way to discover which version of the model delivers more value to the end user. You need to incorporate logging or diagnostics that helps you decide which model "works better".
- **Component test.** ML systems are difficult to divide into components so you need to come up with a clever way of doing this. ML components typically also interface through the data pipeline or shared data, so be aware of any adverse effects of changing one component's behaviour on other components that use its output data.
- **Computer simulation.** Simulation models can be used to provide predictions to the end user or to optimize processes. Simulation models (a digital twin) are also used in situations where it is difficult to collect data from physical systems: the digital twin is used to collect input data and to test how the system responds to predicted output data. The use of digital twins is typical for training reinforcement learning models. Note: for ML projects this is not a Lab method, but a Workshop method.
- **Data analytics.** For ML projects this is not merely a Lab method. Its components "data collection", "apply ML algorithms", "data validation" and "ML model validation" merit separate methods in the framework (see the machine-learning overview page).
- **Hardware validation.** If your ML solution needs to run on hardware components, this might be part of your project to validate the component first.
- **Non-functional test.** A useful overview of the properties to be tested for ML systems is: correctness, overfitting degree, fairness, interpretability, robustness, security, data privacy, and efficiency, along with a literature overview of the methods to test them (Zhang et al., "Machine Learning Testing: Survey, Landscapes and Horizons").
- **Security test.** Also for ML systems you need to find and prioritise vulnerabilities and determine their impact on the confidentiality, integrity and availability of information. Privacy issues are involved if the system processes personal data.
- **System test.** Since the system is self-learning (you did not program the rules yourself) it might be difficult to assess if the system is behaving as required. You need to think about how you will test this beforehand. Usually you will keep aside part of your data for the final testing.
- **Unit test.** See component test, above.
- **Usability testing.** It is also important for ML solutions to test how well the end user is supported in the task the user needs to perform. Make sure you have a proper front-end (UI) through which the user can interact with the ML model and its outcome.

Note: there are separate methods for testing data and the model — data quality check, model validation and model evaluation (see the machine-learning overview page).
