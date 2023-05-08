Download Link: https://assignmentchef.com/product/solved-si671-721-homework-1-speed-dating-match-prediction-and-recommendation
<br>
We will use the speed-dating dataset described in Fisman et al. (2006) for this homework. The dataset was gathered from 552 participants in several speed dating events from 20022004. As is typical, in each of these speed-dating events each attendee met every participant of the opposite gender for a four-minute first-date in which they got to know each other’s interests and determined their compatibility for going out on subsequent dates. At the end of four minutes, all the attendees were asked if they would like to see their date again as well as to rate their date on six attributes: attractiveness, sincerity, intelligence, fun, ambition, and shared interests. The dataset also contains several other features/covariates regarding the participants and their speed-dates.

This homework involves predicting whether an attendee matched with another attendee, and further predicting the missing rating given by an attendee to their dates.

We recommend that you use Jupyter Notebooks and Python libraries Numpy, Sci-kit learn, and Pandas for this homework.

2             Details

This homework is divided into three parts.

<ol>

 <li>Data Exploration.</li>

 <li>Predicting matches.</li>

 <li>Recommending potentially “good” matches.</li>

</ol>

<h2>2.1            Part 1: Data Exploration</h2>

This part of the homework is designed to help you familiarize yourself with the dataset and the context in which it was collected. The insights from this part of the homework can help you in building the prediction and recommendation models for the Parts 2 and 3 of the homework.

a). Read Fisman et al. (2006) closely to understand the context of the data collection.

b). Read SpeedDatingDataKey.pdf to familiarize yourself with the various variable definitions.

c). Perform basic exploratory data analysis, for example,

<ul>

 <li>Visualize data using scatter plots.</li>

 <li>Perform correlation analysis.</li>

 <li>Deal with missing values and outliers.</li>

 <li>Use feature selection techniques to find important features.</li>

</ul>

The main deliverable for this part of the homework is a step-by-step exploration of data along with text describing your conclusions in your Jupyter Notebook. The analysis pipeline described above is just a suggestion and you are welcome to add more or fewer steps as long as it helps you carefully analyze the properties of the dataset.

2.2            Part 2: Predicting Matches

You will build and compare machine learning models to predict if participants X and Y who met for the speed-date actually “matched” i.e. after the event finished they did choose to see their date again. Note that our data contains both the observations, when participant X is the “ID” and Y is the “partner ID”, and when Y is the “ID” and X is the “partner ID”. It’s easy to see that this is an asymmetric prediction task—X might choose to see Y again but Y might not choose to see X again.

We provide you with training dataset which you should use judiciously to train and crossvalidate your models. We also provide a test dataset testML.csv where the “match” label is missing.

We recommend you try at least 4 different machine learning methods/models before choosing the final model. The error-metric that we will use for evaluating your match labels on the test dataset is weighted f1 score (higher is better). Some of the models that you can consider using include,

<ul>

 <li>Random Forests</li>

 <li>Lasso Regression</li>

 <li>Logistic Regression</li>

 <li>Support Vector Machine (SVM)</li>

 <li>Multi-layer perceptron</li>

</ul>

The main deliverable for this part of the homework is a step-by-step analysis of your model building exercise describing clearly how you generated training/validation/test splits from your dataset, how you tuned the model hyperparameters (if any) via cross-validation, and finally, why you chose one model over the other. Your Jupyter notebook should contain the reproducible code for training various models as well as text descriptions of your conclusions after each step.

Your grade on this part of the homework will depend on the accuracy of your model on the test dataset as well as your step-by-step description of how you arrived at your final model. We will evaluate your model using weighted F1-score.

2.3            Part 3: Build recommendation Engine [50 Points]

For the final part of the homework you have to build a recommendation engine where you have to predict the missing ratings (1-10 scale) of a participant X for their date Y. You are encouraged to use the surprise Python library (<a href="http://surpriselib.com">http://surpriselib.com</a><a href="http://surpriselib.com">)</a> and compare atleast 4 algorithms for generating the missing ratings e.g. SVD, SVD++, NMF, k-NN etc.

We provide you with training dataset which you should use judiciously to train and crossvalidate your models. We also provide a test dataset testRec.csv where the partner ratings are absent.

As earlier, your Jupyter Notebook should contain a step-by-step analysis of your model building exercise describing clearly why you chose one model over the other performing necessary cross-validation for tunable parameters.

Your grade on this part of the homework will depend on the accuracy of your model on the test dataset as well as your step-by-step description of how you arrived at your final model. We will evaluate your model using the Mean Absolute Error (MAE) metric.

3             Data Description

Here’s the description of files included with this homework.

<ol>

 <li>csv: This file contains the training data for Part 2 of the homework. It contains 3808 observations and 61 columns/features. The column keys are described in the file SpeedDatingDataKey.pdf.</li>

 <li>csv: This file contains the test data for Part 2 of the homework. Please insert your prediction results in the <strong>match </strong>column in the file.</li>

 <li>csv: This file contains the training data for Part 3 of the homework. The complete training data set has 38340 observations. It contains ratings on a scale of 1-10 given by an attendee with id ‘‘iid’’ to their partner with id ‘‘pid’’.</li>

 <li>csv: This file contains the test data for Part 3 of the homework. Please insert your predicted ratings in the <strong>rate </strong>column in the file.</li>

</ol>

<strong>Note: </strong>Please do not use the data in trainRec.csv to test or evaluate Part 1 or Part2 of the homework. We use different groups of users, thus, their ID won’t match with each other.