# Medical Symptoms Classification

## Introduction

Welcome to the GitHub repository for the project titled "ML meets MD: Diagnosing Coughs and Wounds by Sound".

This project explores the intersection of machine learning and healthcare, focusing on classifying medical symptoms from audio recordings. Specifically, the project aims to differentiate between symptoms such as coughs and infected wounds using audio features and transcriptions. By leveraging various machine learning models, including logistic regression, KNN, SVM, and classification trees, the project evaluates the effectiveness of these methods in accurately classifying symptoms. The findings of this project have the potential to enhance conversational agents in healthcare, providing more accurate and timely diagnoses.



For any communications, you can reach me on my LinkedIn profile: [S. Ziv](https://www.linkedin.com/in/saharziv/)

## Project Overview
### Data Source
The dataset used in this project was obtained from [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/medical-speech-transcription-and-intent/data). Please refer to the original source for any licensing or usage restrictions.

### Exploratory Data Analysis (EDA)
The Exploratory Data Analysis (EDA) section provides an in-depth examination of the dataset, which includes $6661$ audio recordings labeled with various medical symptoms. The focus was narrowed to two specific symptoms: "Cough" and "Infected wound." This subset comprised $599$ recordings, allowing for a more targeted analysis and model training.

I've extracted several key features from the audio files to enhance the model's ability to classify symptoms. These features included the duration of the audio, mean and standard deviation of the Mel-frequency cepstral coefficients (MFCCs), spectral centroid, zero crossing rate, and root mean square (RMS) energy. Additionally, audio quality measures such as clipping, background noise, and speaker volume were incorporated.

### Modeling
The Modeling section focuses on building and evaluating machine learning models to classify medical symptoms based on audio and text features. Three methodologies were applied:

* Modeling with all the extracted audio features, but without any clustering.
* Modeling with all the extracted audio features differently for each cluster.
* Modeling with NLP features, such that each feature is the frequency of a word in the phrase.

Several models were employed for each methodology, including Logistic Regression, K-Nearest Neighbors (KNN), Support Vector Machines (SVM), and Classification Trees. Each model was split to train and test ($70\% - 30\%$).

To optimize performance, hyperparameter tuning was conducted using grid search and cross-validation techniques. The models were evaluated using metrics such as accuracy, sensitivity, specificity and F1-score, providing a comprehensive assessment of their effectiveness. Additionally, confusion matrices were used to visualize the performance and identify areas for improvement. The results highlighted the strengths and limitations of each model, informing decisions on model selection and further refinement.

Among all models and methodologies tested for the audio features analysis, Logistic Regression with Ridge penalty was the best-performing model, achieving accuracy of $71.1\%$ and an F1 score of $72.9\%$ for the non-clustering methodology. In the NLP methodology, the model achieved in $100\%$ accuracy.

### Conclusion

In conclusion, we can say that the best way to predict a symptom using self-reported audio recordings is by transcript it to phrase using speech-to-text software and use the NLP logistic regression model for binary classification, but if we can’t do it for some reason, the classification using the one model with features extracted from the audio files themselves could give good results too.

### Future Work

 It would be more correct to do multiclass classification over all the data and use more models for classification.

## Repository Structure
* /src/: Source code for EDA and modeling classes used in the analysis.
* /data/: A directory for extraction of the audio records downloaded.
* /Presentation and Reports/: Holds all reports sent throughout the course.
* README.md: Project overview and documentation.

### How to Run
1. Clone the repository:
```
git clone https://github.com/Sahar-Zi/Medical-Speech.git
```
2. Install the required dependencies:
```
pip install -r requirements.txt
```
3. Download and extract the dataset to the /data/ directory as described in the Data Source section.

4. Run the python notebook: `Medical_Symptom_Project.ipynb`

### Contributing
I welcome contributions to this project. Please fork the repository and submit a pull request with your changes.

### Acknowledgments
I would like to thank all contributors for this project and especially for my supervisor Dr. Itai Dattner for his support and valuable feedback.
