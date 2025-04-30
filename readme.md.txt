Heart Disease Prediction Project - README

Overview





Purpose: This project predicts whether a patient has heart disease using machine learning models.



Files: Includes Heart_Disease_Classification (2).html (notebook), app.py (backend), model.pkl (model), and Heart Disease Classifier.html (frontend).

Project Flow





Notebook: Heart_Disease_Classification (2).html loads the dataset, trains models (SVC, Random Forest, AdaBoost, GradientBoosting), and selects the best (GradientBoosting with 74% accuracy).



App: app.py uses model.pkl to predict based on form inputs, displaying results on the HTML page.



Description:
The Heart Disease Prediction Project is a machine learning initiative designed to predict whether a patient is likely to have heart disease based on various health metrics. This project leverages a dataset containing features such as age, sex, resting blood pressure, serum cholesterol, maximum heart rate, and other clinical indicators, with the goal of classifying patients into two categories: those with heart disease (labeled as 0) and those without (labeled as 1). The primary motivation is to assist healthcare professionals by providing a tool that can analyze patient data and offer preliminary insights, potentially aiding in early diagnosis and treatment planning.

The project is structured around a Jupyter notebook titled Heart_Disease_Classification (2).html, which serves as the foundation for data exploration, model development, and evaluation. The notebook begins with data visualization, using tools like Seaborn to create plots (e.g., the correlation between age and maximum heart rate), revealing patterns such as older patients with lower heart rates being more likely to have heart disease. This exploratory phase is followed by data preparation, where the dataset is split into training (80%) and testing (20%) sets using the train_test_split function from scikit-learn. Four machine learning algorithms—Support Vector Machine (SVC), Random Forest, AdaBoost, and Gradient Boosting—are trained and evaluated using a custom fit_eval_model function that generates classification reports and confusion matrices.

Among these, the GradientBoostingClassifier emerged as the best performer, achieving 74% accuracy with a precision of 79% and recall of 73% for detecting disease cases. This model’s strength lies in its ability to iteratively improve predictions by building multiple decision trees, adjusting for errors using gradient descent. The trained model is saved as model.pkl, enabling its integration into a web application. The backend, implemented in app.py using the Flask framework, loads this model to process user inputs from a form embedded in Heart Disease Classifier.html. Users enter health metrics, submit the form, and receive a prediction indicating whether heart disease is likely or not.

However, the project faces a significant challenge: the web application consistently predicts "not likely" (1) regardless of input, suggesting a potential issue with the model’s training data or input processing. This bug may stem from an imbalance in the training dataset or a mismatch between the form inputs and the model’s expected feature set. Future improvements could involve retraining the model with balanced data, tuning hyperparameters (e.g., increasing the number of trees in GradientBoosting), and explicitly cleaning the dataset (e.g., removing outliers with df.dropna()). Additionally, ensuring the HTML file is correctly located (ideally in a templates folder) and matches the model’s input requirements will enhance functionality.

Overall, this project demonstrates a practical application of machine learning in healthcare, combining data analysis, model training, and web deployment. With refinements, it could become a valuable tool for preliminary heart disease screening, though further testing and validation are needed to address current limitations and improve accuracy.