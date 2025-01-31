---
layout: page
title: Graduate Project
nav_order: 3
description: Specifications for the grad project for Data 200.
markdown: kramdown
---
# Graduate Project
{:.no_toc}

* TOC
{:toc}

## Introduction

The graduate project is **offered only to students enrolled in Data C200, CS C200A, or Data 200S**. Other students are welcome to explore the questions and datasets in the project for personal learning, but their work will not be graded or counted towards their final grades.

The purpose of the project is to give students experience in both open-ended data science analysis and research in general.

## Deliverables

The graduate project element will require the following deliverables:

### Upcoming Deliverables:

- **Group Formation + Research Proposal:** You will form a project group and submit a google form stating your intended topic and a brief implementation plan. Please see [below](#group-formation--research-proposal) for more information.

### Future Deliverables (subject to change):

- **Checkpoint 1: EDA + Internal Peer Review 1:** Submit a write-up and code for Exploratory Data Analysis on your dataset. Additionally, submit an internal peer review. More information [below](#checkpoint-1-eda--internal-peer-review).
- **Checkpoint 2: Mandatory Check-In:** Write a one-pager of your progress, focusing on the modeling approaches your team explored, and review it with a course staff member. Further details [below](#checkpoint-2-mandatory-check-in).
- **Project Report First Draft + Internal Peer Review 2:** Submit the first draft of your report, detailing your EDA and modeling efforts, along with any necessary code. An internal peer review is also required.
- **External Peer-Review:** Provide feedback on other project teams' work.
- **Final Project Report:** Submit the final project report, including all necessary code. Ensure all relevant feedback from the first draft and external peer reviews are incorporated. Additionally, you are required to make a brief 5-minute YouTube video recording of the project.


### Teamwork

**You must work in groups of two or three students.** In order to give everyone experience in collaborating on a data science project, individual projects are not allowed. Everyone in the same group will receive the same grade (except for exceptional circumstances).

## Timeline and Grading Breakdown

<!-- [Internal Peer Review](https://forms.gle/cied6ZzmBToj3ARP9) -->

| Deadline (at 11:59 PM Pacific) | Event / Deliverable                        | Link                                                           | Grading Weight |
|--------------------------------|--------------------------------------------|----------------------------------------------------------------|----------------|
| 3/15                           | Research Proposal and Project Groups Due   | [Google Form](https://forms.gle/DcBp3ZbM8TpTfSRD6)             | 5%             |
| 3/22                           | Checkpoint 1: EDA + Internal Peer Review 1 |    | 10%            |
| Week of 4/8                    | Checkpoint 2: Mandatory Check-in with TA   |                                                                | 7.5%           |
| 4/19                           | Internal Peer Review 2 Due                 |                                                                | 20%            |
| 4/26                           | First Draft of Final Report Due            |                                                                | 7.5%           |
| 5/3                            | External Peer Review Due                   |                                                                | 7.5%           |
| 5/10                           | Final Project Report and Presentation Video|                                                                | 50%            |

### Late Policy
- **No Extensions for First Draft**: The first draft cannot be submitted late as it is crucial for the peer review process.
- **Final Report and Presentation Video**: Late submissions incur a 10% daily penalty, up to a maximum of two days. Submissions are rounded to the nearest day (e.g., 2 minutes late counts as 1 day late).
- **Peer Reviews and Other Deliverables**: Must be submitted on time; no extensions are permitted.


## Datasets

This section contains the topics we will provide to you to explore your research questions. Please choose one of the following datasets to work on. **You will be expected to complete all (2) tasks provided for your chosen dataset.**

### Accessing Datasets

All of the provided datasets can be found in the Datahub directory `shared/sp24_grad_project_data`. You can access the data directly from Datahub. If you wish to work on the project locally, you can also download the files containing the datasets for each topic by right-click on the file in JupyterLab and select "Copy Download Link". If you choose to train more complex models, DataHub might not have enough hardware resources or memory, in which case you can use [Google Colab](https://colab.google/){:target="_blank"} or your local machine. If you would like to use Google Colab, feel free to check out this [link](https://stackoverflow.com/questions/48376580/how-to-read-data-in-google-colab-from-my-google-drive){:target="_blank"} to get started.

### Topic 1: Computer Vision
In disaster situations, it is important for emergency response efforts to have access to quick and accurate information about an area in order to respond effectively. This project will explore how data science techniques can be useful for such efforts.

#### Project Goals
{:.no_toc}
- Learn to work with image data by learning to use common feature extraction techniques like Sobel edge filtering.
- Learn to work on real-world data with common complexities such as class imbalance, low signal-to-noise ratio, and high dimensional data.
- Learn how to design effective preprocessing and featurization pipelines for solving difficult machine learning tasks.

#### Mission
{:.no_toc}
You have been hired by a crisis response agency to help assist them with your impressive data science skills! The agency has found that using satellite imagery is highly useful for supplying information for their response efforts. Unfortunately, however, annotating these high-resolution images can be a slow process for analysts. Your mission is to help address this challenge by developing an automatic computer vision approach!

#### Dataset Description
{:.no_toc}
The agency would like you to develop your approach on their internal dataset, derived from the [xView2 Challenge Dataset](https://xview2.org/){:target="_blank"}. This dataset contains satellite images of buildings after various natural disasters. The buildings are labeled based on the level of damage sustained on a scale ranging from 0 (no damage) to 3 (destroyed).

You can access all of the data within the `./satellite-image-data` directory. The dataset consists of the following folders for different natural disasters
1. `midwest-flooding`
2. `socal-fire`
3. `hurricane-matthew`

Within each folder is a zip file `train_images.npz` containing the satellite images as numpy arrays and a `train_labels.npy` file with corresponding damage level labels.

> Testing: In the main directory, there are also the `test_images_hurricane-matthew.npz` and `test_images_flooding-fire.npz` zip files. The first contains test images from the `hurricane-matthew` disaster and the latter consists of a combination of test images from `midwest-flooding` and `socal-fire`.

#### Getting Started
{:.no_toc}
To help you with onboarding, the agency has provided a starter notebook [`starter.ipynb`](https://data100.datahub.berkeley.edu/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2FDS-100%2Fsp24-student&urlpath=lab%2Ftree%2Fsp24-student%2Fgrad-proj%2Fsatellite-images%2Fstarter.ipynb&branch=main){:target="_blank"} which will introduce you to the dataset and some useful internal tools. After completing the onboarding assignment you will be comfortable with the following:
1. Loading and visualizing data using tools from `data_utils.py`
2. Processing different color channels in the dataset images.
3. Extracting feature information from images using tools from `feature_utils.py`.

#### Exploratory Data Analysis
{:.no_toc}
Now that you have successfully been onboarded, the agency would like you to start performing some exploratory data analysis to build an initial understanding of the data. As part of the exploratory data analysis, the agency is interested in understanding certain aspects of the dataset better. Specifically, they are looking for:

- Basic statistics about the dataset, such as the number of images per disaster type and the distribution of image sizes and damage labels.
- Insights into useful image features for classifying images based on disaster type or damage level. Previous interns have found color information to be potentially useful. You are tasked with verifying this and exploring whether color features can effectively differentiate:
    - `midwest-flooding` from `socal-fire` images.
    - Damage levels 1 and 3 within the `hurricane-matthew` dataset.

Please prepare an EDA report to present to the agency leadership with the above in mind.

#### Project Tasks
{:.no_toc}
Now that leadership is pleased with your initial EDA report and confident in your data science ability, they would like you to assist the agency with various tasks. *Please complete Task A first and then Task B.*

#### *Task A: Disaster Type Classification*
{:.no_toc}
The agency consists of different subdivisions for assisting with different disaster types, e.g., fires, floods, etc. In the event of a disaster, the agency mounts its response effort by first assessing the type of disaster and then requesting the appropriate subdivision to assist with the disaster.

Your task is to assist the agency with making this initial call quickly by automatically classifying images based on the disaster scenario. Specifically, your role will be to build a classifier that can distinguish images from the `midwest-flooding` disaster and the `socal-fire` disaster.

To assess your performance, please submit predictions for the `test_images_flooding-fire.npz` images. This should be in a csv file `test_images_flooding-fire_predictions.csv` consisting of a single column with no header, with a 0 to indicate a `midwest-flooding` prediction and a 1 to indicate a `socal-fire` prediction. The prediction in row *i* should correspond to the *ith* image.

#### *Task B: Damage Level Classification*
{:.no_toc}
The agency needs to know how severe a disaster is in order to allocate resources for a response effectively. The agency is especially concerned with human lives and uses building damage as an important metric for disaster severity.

Your task is to assist the agency by automatically detecting the building damage level after a disaster. Specifically, create a damage level classifier for the `hurricane-matthew` disaster.

To assess your performance, please submit predictions for the `test_images_hurricane-matthew.npz` images. This should be in a CSV file `test_images_hurricane-matthew_predictions.csv` consisting of a single column with no header, with a 0-3 prediction of the damage level. The prediction in row *i* should correspond to the *i*th image.

#### Resources
{:.no_toc}
To assist you in your efforts the agency has compiled the following list of resources:
- For more background about the dataset you can look at the [paper](https://arxiv.org/pdf/1911.09296.pdf){:target="_blank"} associated with the dataset.
- For image processing, [scikit-image](https://scikit-image.org/){:target="_blank"} is a very useful library. This [tutorial](https://www.kaggle.com/code/bextuychiev/full-tutorial-on-image-processing-in-skimage){:target="_blank"} may be helpful for learning how to use the library.
- For problems with imbalanced classes, the [imblearn](https://imbalanced-learn.org/stable/index.html){:target="_blank"} library has useful tools and examples.


### Topic 2: Natural Language Processing

A common task in real-life data analysis involves working with text data.
In this project, we will work with a dataset consisting of natural language questions asked by humans and answers provided by chatbots.

#### Project Goals
{:.no_toc}
- Prepare you to work with text data by learning common techniques like embedding generation, tokenization, and topic modeling.
- Work with real-world data in its targetted domain. The data is non-trivial in both size and complexity.
- Ask open-ended questions and answer them using data at hand.

#### Dataset Description
{:.no_toc}
The source dataset link is [here](https://huggingface.co/datasets/lmsys/chatbot_arena_conversations){:target="_blank"}. The author describes the dataset as follows:

> This dataset contains 33K cleaned conversations with pairwise human preferences. It is collected from 13K unique IP addresses on the Chatbot Arena from April to June 2023. Each sample includes a question ID, two model names, their full conversation text in OpenAI API JSON format, the user vote, the anonymized user ID, the detected language tag, the OpenAI moderation API tag, the additional toxic tag, and the timestamp.

[Chatbot Arena](https://chat.lmsys.org/){:target="_blank"} is a platform where users can ask questions and two chatbots will provide answers. The user then votes on which chatbot provided the best answer. The dataset contains the questions, the answers, and the user votes.

You can find the processed dataset in `./chatbot-arena-conversations.jsonl.gz`. The dataset is in JSON line format and compressed using gzip. It has gone through the following preprocessing steps to make analysis easier:

- Removed non-English conversations.
- Removed conversations with more than one round.
- Removed conversations classified as toxic or harmful.

The dataset you will be working with contains `25322` rows (out of `33000` total rows) and `7` columns ([example row](https://gist.github.com/simon-mo/25c5d532bccc7f28b404cffdfe719e6e#file-example-row-json){:target="_blank"}). The columns are:

- `question_id`: A unique identifier for the question.
- `model_a`: The name of the first chatbot model.
- `model_b`: The name of the second chatbot model.
- `winner`: The name of the chatbot model that won the user vote.
- `judge`: The anonymized user ID that voted.
- `conversation_a`: The conversation between the user and `model_a`.
- `conversation_b`: The conversation between the user and `model_b`.

There are two auxiliary datasets that you can use to help with your analysis:

- `./chatbot-arena-prompts-embeddings.npy` contains the 256-dimensional text embeddings for each of the human questions. The embeddings are generated using OpenAI's `text-embedding` model. We will explain what embeddings are and how you can use them later.
- `./chatbot-arena-gpt3-scores.jsonl.gz` ([example row](https://gist.github.com/simon-mo/25c5d532bccc7f28b404cffdfe719e6e#file-example-aux-row-json){:target="_blank"}) contains labels for the dataset you can use for later modeling tasks. It has the following fields:
  - `question_id`: The unique identifier for the question, as seen in `./chatbot-arena-conversations.jsonl.gz`.
  - `prompt`: The extracted human question. This is equivalent to the first message in `conversation_a` and `conversation_b` in `./chatbot-arena-conversations.jsonl.gz`.
  - `openai_scores_raw_choices_nested`: The response from OpenAI GPT 3.5 model (see later for the prompt). It contains the evaluated topic model, the reason for a hardness score from 1 to 10, and the value. For each prompt, we have 3 responses from GPT 3.5 because it is a probablistic model. In fact, you will find in real world there are common multiple labels from different annotators for ground truth data. We extracted the fields into the columns below.
  - `topic_modeling_1`, `topic_modeling_2`, `topic_modeling_3`: The topic modeling for the first, second, and third response. Each topic should have two words.
  - `score_reason_1`, `score_reason_2`, `score_reason_3`: The reason for the hardness score for the first, second, and third response.
  - `score_value_1`, `score_value_2`, `score_value_3`: The hardness score for the first, second, and third response.

We used [this prompt](https://gist.github.com/simon-mo/25c5d532bccc7f28b404cffdfe719e6e#file-prompt-md){:target="_blank"} to generate the responses. You are welcome to generate your own ground truth data. You can generate your own embeddings following [this](https://gist.github.com/simon-mo/25c5d532bccc7f28b404cffdfe719e6e#file-using-your-own-embeddings-md){:target="_blank"} guide.

#### Exploratory Data Analysis
{:.no_toc}
For the EDA tasks, tell us more about the data. What do you see in the data? Come up with questions and answers about them. For example, what is the win rate of GPT4?  What are the most common topics? Do different judges have different preferences? What are the most common topics? What are the most common reasons for a question being hard?

#### Project Tasks
{:.no_toc}
Now, we aim to better understand the different chatbot models! Please complete both Task A and B. We have included example questions to consider, but you are expected to come up with your own questions to answer.

For both task, you will be working with the data provided. But you are also expected to perform prediction on a hold out set. You can find the data in `arena-validation-set-prompt-only.jsonl.gz` in the same directory. The data contains fields `question_id`, `prompt`, `model_a`, and `model_b`. You are expected to predict the winner and the hardness score for task A and B respectively. You should submit your final prediction as a `csv` file with four columns `question_id`, `winner`, `hardness_score`. The `winner` column should be one of the four values: `model_a`, `model_b`, `tie`, or `tie (bothbad)`. The `hardness_score` should be an integer from 1 to 10.

#### *Task A: Modeling the Winning Model*
{:.no_toc}
Given a prompt, can we predict which model's response will win the user vote? You can start by analyzing the length, textual features, and embeddings of the prompt. You should also explore the difference in output of the different models. For modeling, you can use logistic regression or other modeling techinque to perform classification to redict the winner for the hold out set given `prompt`, `model_a` and `model_b`. You should also evaluate the model using appropriate metrics.

One hint would be to utilize topic modeling data by first clustering prompts given their embeddings, then for each cluster, train a model to predict the winner. Also, feel free to use the hardness score to help with the prediction.

#### *Task B: Hardness Prediction*
{:.no_toc}
While we provide the hardness score generated by GPT3.5, can you explore whether such scoring is useful and valid? For hardness score, we want it to be an integer value from 1 to 10. For example, if a prompt's score is 1, we expect the weak model to be able to answer the question. If the score is 10, we expect the question to be hard, maybe only GPT4 can answer it.

You can start by analyzing the embeddings and the topic modeling data. You can then use linear regression to predict the hardness score, using existing or new features.

You should also evaluate the model using appropriate metrics. One challenging aspect here is that the output score should be integer value, while linear regression is used for continuous data.

#### Getting Started
{:.no_toc}
To get started, we provide a notebook [`nlp-chatbot-starter.ipynb`](https://github.com/DS-100/sp24-dev/blob/main/proj_final/nlp-chatbot-analysis/nlp-chatbot-starter.ipynb){:target="_blank"} that demonstrates how to load and inspect the data.

Additionally, here are some example questions about the project that you are welcome to explore.

> Modeling: Perform some modeling tasks given our ground truth labels. Can you train a logistic regression model to predict the winner given embeddings? How about a K-means clustering model to cluster the questions? Can you use linear regression to predict the hardness score? We expect you to demonstrate how the well model works and how to evaluate them. You should justify the choice of model and the evaluation metrics. You should also discuss the limitations of the model and how to improve them.

> Analysis: By leveraging the question embeddings, can we find similar questions? How repeated are the questions in the dataset? Can you reproduce the Elo score rating for the chatbots and come up with a better ranking? How can we make sense of the data overall?

#### Resources
{:.no_toc}
- [Joey's EDA and Elo rating modeling](https://colab.research.google.com/drive/1KdwokPjirkTmpO_P1WByFNFiqxWQquwH){:target="_blank"} is a great resource to get started with the EDA. Note that (1) the plot is made with Plotly, we recommend you to reproduce the plot with Matplotlib or Seaborn, and (2) the Elo rating is a good modeling task to reproduce but we expect you to do more than just that (for example, demonstrate how Elo rating works and how to calculate it in your report).

- [An intuitive introduction to text embeddings](https://stackoverflow.blog/2023/11/09/an-intuitive-introduction-to-text-embeddings/){:target="_blank"} is a good resource to understand what is text embeddings and how to use them.

- [Elo rating system](https://en.wikipedia.org/wiki/Elo_rating_system){:target="_blank"} and [Bradley-Terry model](https://en.wikipedia.org/wiki/Bradley%E2%80%93Terry_model){:target="_blank"} are essential to model a ranking among the pairwise comparison.

- [Huggingface pipeline](https://huggingface.co/docs/transformers/en/main_classes/pipelines){:target="_blank"} has many implementations of common NLP tasks for you to use, including sentiment analysis, summarization, text classification, etc.

- [spaCy](https://spacy.io/usage/spacy-101){:target="_blank"} is a wonderful library containing classifical NLP tasks like tokenization, lemmatization, etc.

## Group Formation + Research Proposal

The first deliverable of your group project is just to form your group, choose a dataset, and submit your implementation plan to [this google form](https://forms.gle/DcBp3ZbM8TpTfSRD6){:target="_blank"} by 11:59 pm on 3/15. The implementation plan should consist of a series of steps for completing the project along with a timeline. You may form groups of 2 or 3 people with any Data 200/200A/200S student.

## Checkpoint 2:
The purpose of this checkpoint is to ensure you are making progress and are on schedule to submit the first draft of the project in approximately two weeks time. You will be required to submit a pdf document summarizing 1) all of your progress so far and 2) future plans. Guiding questions for the content of the document are detailed below. You will be required to submit the report to Gradescope before the meeting. The staff member will skim the report before the meeting and give you guidance on the project as a whole. Please refer to the [rubrics](#rubrics) section for the grading breakdown. 

### Progress So Far
- What type of data were you exploring?
- What were your EDA questions? 
- What was the granularity of the data?
- What did the distribution of the data look like? Were there any outliers? Were there any missing or invalid entries?
- If the data was not in a featurized format, what features did you explore and why?
- Was there any correlation between the variables you were interested in exploring?
- How did you try to cleanly and accurately visualize the relationship among variables?
- Did you need to perform data transformations?

### Future Plans
- What model do you plan on using and why?
- Will your model require hyperparameter tuning? If so, how will you approach it?
- How will you engineer the features for your model? What are the rationales behind selecting these features?
- How will you perform cross validation on your model?
- What loss metrics are you going to use to evaluate your model?
- From a bias-variance tradeoff standpoint, how will you assess the performance of your model? How will you check if it is overfitting?
- How will you improve your model based on the outcome?

## Rubrics
This section includes a rubric for how different project deliverables are going to be graded. This section will be updated as we get further along the project timeline.

### Group formation + Research Proposal (5%)
- Short paragraph description of implementation plan and timeline (2%).
- Forming teams by the deadline (3%).

### Checkpoint 2: Mandatory Check-In (7.5%)
- Exploratory Data Analysis (1.5%).
- Feature Engineering (2%).
- Modelling Approaches (3%).
- Preliminary Results (1%).