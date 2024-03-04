---
layout: page
title: Graduate Project
nav_order: 3
description: Specifications for the grad project for Data 200.
markdown: kramdown
---
# Graduate Project
{:.no_toc}

<!--### <span style="color:red"> ⚠️ Warning: This webpage is under construction; nothing here is finalized until it is on ds100.org/fa23/gradproject </span>
{:.no_toc} -->

* TOC
{:toc}

## Introduction

The graduate project is offered only to students enrolled in Data C200, CS C200A, or Data 200S. Other students are welcome to explore the questions and datasets in the project for personal learning, but their work will not be graded or counted towards their final grades.

The purpose of the project is to give students experience in both open-ended data science analysis and research in general. In this project, you will work with **one or any combination** of the following datasets provided to you to explore research questions that you define.

<!-- **Project criteria**: In addition to the general guidelines, each dataset option below has its own set of additional requirements for Report Format and Submission. Be sure to consult the correct section for your project option.) 0-->


## Deliverables

There are **six** deliverables in the graduate project element of the course.
<ul>
<li><b>Group Formation + Research Proposal:</b> You will form a project group and will submit a google form stating your research proposal. Please see <a href="#group-formation--research-proposal">below</a> for more information. </li>
<li><b>Checkpoint 1: EDA + Internal Peer Review:</b> You will need to submit a write-up + code for Exploratory Data Analysis on your dataset. You will also have to submit an internal peer review. Please see <a href="#checkpoint-1-eda--internal-peer-review">below</a> for more information. </li>
<li><b>Checkpoint 2: Mandatory Check-In:</b> You will need to write a one-pager of your progress (with a focus on modeling approaches your team explored) and review it with a course staff member. Please see <a href="#checkpoint-2-mandatory-check-in">below</a> for more information. </li>
<li><b>Checkpoint 3: Project Report First Draft + Internal Peer Review:</b> This will be your first draft; you will be required to submit a report of your EDA and modeling along with any code necessary to reproduce your results. You will also have to submit an internal peer review. More information will be announced later.</li>
<li><b>External Peer-Review:</b> You will need to provide other project teams with feedback on their projects. More information will be announced later.</li>
<li><b>Final Project Report:</b> You will submit the final project report. You will need to submit a report (as well as all necessary code), ensuring you incorporate all relevant feedback from the first draft and external peer review. You will also be required to make a brief 5-minute YouTube video recording of the project. More information will be announced later.</li>
</ul>

### Teamwork

**You must work in a group with one or two other students.** In order to give everyone experience in collaborating on a data science project, individual projects are not allowed. We have an [Ed post](https://edstem.org/us/courses/42444/discussion/3373220) for teammate search. Everyone in the same group will receive the same grade (except for exceptional circumstances).

## Timeline and Grading Breakdown

| Deadline (at 11:59pm Pacific)| Event / Deliverable | Link | Grading Weight |
|--------------------------	|---------------------------------------------	|---------------------------------------------	|-----------|
| 3/15 | Research Proposal and Project Groups Due | [Google Form](https://forms.gle/KnJPVvbcr6j6wt7GA) | 5% |
| 3/22 | Checkpoint 1: EDA + Internal Peer Review 1 Due | [Checkpoint 1](https://www.gradescope.com/courses/564792/assignments/3537706), [Internal Peer Review](https://forms.gle/TMbH2c7Ukpn2marM9)| 10% |
| Week of 4/8 | Checkpoint 2: Mandatory Check-in with TA  | | 7.5% |
| 4/19 | Internal Peer Review 2 Due | | 20% |
| 4/26 |	First Draft of Final Report Due | | 7.5% |
| 4/29 |	External Peer Review Opens | | 7.5% |
| 5/3 |	External Peer Review Due | | 7.5% |
| 5/10 | Final Project Report Due, Presentation Video Due | | 50% |

### Late Policy

* You may submit the **first draft**, **final report**, and the **presentation video** late with a 10% penalty (applying only to that portion of your project grade) for each day it is late. You may submit up to two days late. Submission times are rounded up to the next day. That is, 2 minutes late = 1 day late.
* Internal and external peer reviews as well as other project deliverables must be completed on time (there is no grace period).


## Datasets

This section contains the datasets we will provide to you to explore your research questions.

- You must incorporate **at least one** of the provided datasets.
- You are welcome to **bring in additional datasets** to complement the datasets provided here, but you must cite the sources and clearly describe the content of any additional data you use in the final report.

In general, if you're drawing any conclusions regarding causality, please be sure to consult the [extra resources on causal inference](#extra-resources-causal-inference).

### Accessing Datasets

All the datasets provided by us can be found in the Datahub directory `shared/sp24_grad_project_data`. You can access the data directly from Datahub. If you wish to work on the project locally, you can also download the files containing the datasets for each topic. As you train more complex model, DataHub might not have enough hardware resource or memory, that case you are welcomed to use Google Colab or your local machine.

### Topic 1: Computer Vision
In disaster situations, it is important for emergency response efforts to have access to quick and accurate information about an area in order to respond effectively. This project will explore how data science techniques can be useful for such efforts.

#### Sections
The specifications for this project contains the following sections:
* [Mission](#mission)
* [Dataset Description](#dataset-description)
* [Getting Started](#getting-started)
* [Exploratory Data Analysis](#exploratory-data-analysis)
* [Project Tasks](#project-tasks)
* [Resources](#resources)
* [Project Goals](#project-goals)

#### Mission
You have been hired by a crisis response agency to help assist them with your impressive data science skills! The agency has found that using satellite imagery is highly useful for supplying information for their response efforts. Unfortunately however, annotating these high resolution images can be a slow process for analysts. Your mission is to help address this challenge by developing an automatic computer vision approach.

#### Dataset Description
The agency would like you to develop your approach on their internal dataset, derived from the [xView2 Challenge Dataset](https://xview2.org/). This dataset contains satellite images of buildings after various natural disasters. The buildings are labeled based on the level of damage sustained on a scale ranging from 0 (no damage) to 3 (destroyed).

You can access all of the data within the `/home/jovyan/shared/satellite-image-data` directory on datahub. The dataset consists of the following folders for different natural disasters
1. `midwest-flooding`
2. `socal-fire`
3. `hurricane-matthew`

Within each folder is a zip file `train_images.npz` containing the satellite images as numpy arrays and a `train_labels.npy` file with corresponding damage level labels.

#### Getting Started
To help you with onboarding, the agency has provided a starter notebook `starter.ipynb` which will introduce you to the dataset and some useful internal tools. After completing the onboarding assignment you will be comfortable with the following:
1. Loading and visualizing data using tools from `data_utils.py`
2. Processing different color channels in the dataset images.
3. Extracting feature information from images using tools from `feature_utils.py`.

#### Exploratory Data Analysis
Now that you have successfully been onboarded, the agency would like you to start performing some exploratory data analysis to build some initial understanding of the data. As part of the exploratory data analysis, the agency is interested in understanding certain aspects of the dataset better. Specifically, they are looking for:

- Basic statistics about the dataset, such as the number of images per disaster type and the distribution of image sizes and damage labels.
- Insights into useful image features for classifying images based on disaster type or damage level. Previous interns have found color information to be potentially useful. You are tasked with verifying this and exploring whether color features can effectively differentiate:
    - `midwest-flooding` from `socal-fire` images.
    - Damage levels 1 and 3 within the `hurricane-matthew` dataset.

Please prepare an EDA report to present to the agency leadership with the above in mind.

#### Project Tasks
Now that leadership is pleased with your initial EDA report and confident in your data science ability, they would like you to assist the agency with various tasks.

##### Task A: Disaster Type Classification
The agency consists of different subdivisions for assisting with different disaster types, e.g., fires, floods, etc. In the event of a disaster, the agency mounts its response effort by first assessing the type of disaster and then requesting the appropriate subdivision to assist with the disaster.

Your task is to assist the agency with making this initial call quickly by automatically classifying images based on the disaster scenario.

##### Task B: Damage Level Classification
The agency needs to know how severe a disaster is in order to allocate resources for a response effectively. The agency is especially concerned with human lives and uses building damage as an important metric for disaster severity.

Your task is to assist the agency by automatically detecting the building damage level after a disaster.

#### Resources
To assist you in your efforts the agency has compiled the following list of resources
- For more background about the dataset you can look at the [paper](https://arxiv.org/pdf/1911.09296.pdf) associated with the dataset.

- For image processing, [scikit-image](https://scikit-image.org/) is a very useful library. This [tutorial](https://www.kaggle.com/code/bextuychiev/full-tutorial-on-image-processing-in-skimage) may be helpful for learning how to use the library.

- For problems with imbalanced classes, the [imblearn](https://imbalanced-learn.org/stable/index.html) library has useful tools and examples.

#### Project Goals
In addition to greatly helping out the agency, by accepting this job you will
- Learn to work with image data by learning to use common feature extraction techniques like Sobel edge filtering.
- Learn to work on real world data with common complexities such as class imbalance, low signal to noise ratio, and high dimensional data.
- Learn how to design effective preprocessing and featurization pipelines for solving difficult machine learning tasks.

### Topic 2: Natural Language Processing
A commont task in real life data analysis involves working with text data.
In this project, we will work with a dataset consisting natural language questions asked by human and answers provided by chatbots.

The goal of this project is to:

- Prepare you to work with text data by learning common techniques like embedding generation, tokenization, and topic modeling.
- Work with real world data in its targetted domain. The data is non-trivial in both size and complexity.
- Ask open ended questions and answer them using data at hand.

#### Dataset Description


The source dataset comes from https://huggingface.co/datasets/lmsys/chatbot_arena_conversations. The author describes the dataset as follows:

> This dataset contains 33K cleaned conversations with pairwise human preferences. It is collected from 13K unique IP addresses on the Chatbot Arena from April to June 2023. Each sample includes a question ID, two model names, their full conversation text in OpenAI API JSON format, the user vote, the anonymized user ID, the detected language tag, the OpenAI moderation API tag, the additional toxic tag, and the timestamp.

[Chatbot Arena](https://chat.lmsys.org/) is a platform where users can ask questions and two chatbots will provide answers. The user then votes on which chatbot provided the best answer. The dataset contains the questions, the answers, and the user votes.

You can find the processed dataset in `./chatbot-arena-conversations.jsonl.gz`. The dataset is in JSON line format and compressed using gzip. It has gone through the following preprocessing steps to make analysis easier:

- Removed non-English conversations.
- Removed conversations with more than one round.
- Removed conversations classified as toxic or harmful.

The dataset you will be working with contains `25322` rows (out of `33000` total rows) and `7` columns. The columns are:

- `question_id`: A unique identifier for the question.
- `model_a`: The name of the first chatbot model.
- `model_b`: The name of the second chatbot model.
- `winner`: The name of the chatbot model that won the user vote.
- `judge`: The anonymized user ID that voted.
- `conversation_a`: The conversation between the user and `model_a`.
- `conversation_b`: The conversation between the user and `model_b`.

<!-- collapse -->
<details>
  <summary>An example of the data is as follows:</summary>
  ```json
{
  "question_id": "c0fc42c6f5f14f2aa5a89f71f8553730",
  "model_a": "vicuna-13b",
  "model_b": "koala-13b",
  "winner": "model_a",
  "judge": "arena_user_973",
  "conversation_a": [
    {
      "content": "Count from 1 to 10 with step = 3",
      "role": "user"
    },
    {
      "content": "1, 4, 7, 10\n\nCounting with a step of 3 means that you will increase the number by 3 each time. So, the first number is 1, the next is 4 (1 + 3), the next is 7 (4 + 3), and so on.",
      "role": "assistant"
    }
  ],
  "conversation_b": [
    {
      "content": "Count from 1 to 10 with step = 3",
      "role": "user"
    },
    {
      "content": "1, 4, 7, 10",
      "role": "assistant"
    }
  ]
}
```
</details>

There are two axuliary dataset that you can use to help with your analysis:

- `./chatbot-arena-prompts-embeddings.npy` contains the 256 dimensional text embeddings for each of the human question. The embeddings are generated using OpenAI's `text-embedding` model. We will explain what is embedding and how can you use them later in this notebook. It has shape (25322, 256) and have dtype('float32').
- `./chatbot-arena-gpt3-scores.jsonl.gz` contains labels for the dataset you can use for later modeling tasks. It has the following fields:
  - `question_id`: The unique identifier for the question, as seen in `./chatbot-arena-conversations.jsonl.gz`.
  - `prompt`: The extracted human question. This is equivalent to the first message in `conversation_a` and `conversation_b` in `./chatbot-arena-conversations.jsonl.gz`.
  - `openai_scores_raw_choices_nested`: The response from OpenAI GPT 3.5 model (see later for the prompt). It contains the evaluated topic model, reason for a hardness score from 1 to 10, and the value. For each prompt, we have 3 responses. We extracted the fields into the following columns.
  - `topic_modeling_1`, `topic_modeling_2`, `topic_modeling_3`: The topic modeling for the first, second, and third response. Each topic should have two words.
  - `score_reason_1`, `score_reason_2`, `score_reason_3`: The reason for the hardness score for the first, second, and third response.
  - `score_value_1`, `score_value_2`, `score_value_3`: The hardness score for the first, second, and third response.

<details>
<summary>An example of the data is as follows:</summary>

```json
{
  "question_id": "58210e39b3fd4441a2bd4a518bb44c2d",
  "prompt": "What is the difference between OpenCL and CUDA?",
  "openai_scores_raw_choices_nested": [
    {
      "finish_reason": "stop",
      "index": 0,
      "logprobs": null,
      "message": {
        "content": "{\n    \"topic_modeling\": \"Technical Comparison\",\n    \"score_reason\": \"This prompt requires the AI to accurately compare and contrast two distinct technologies, OpenCL and CUDA. It assesses the AI's factual accuracy and knowledge of these technologies, as well as its ability to articulate the differences between them.\",\n    \"score_value\": 9\n}",
        "role": "assistant",
        "function_call": null,
        "tool_calls": null
      }
    },
    {
      "finish_reason": "stop",
      "index": 1,
      "logprobs": null,
      "message": {
        "content": "{\n    \"topic_modeling\": \"Software Comparison\",\n    \"score_reason\": \"This prompt assesses the AI's factual accuracy in distinguishing between two similar but distinct software frameworks.\",\n    \"score_value\": 8\n}",
        "role": "assistant",
        "function_call": null,
        "tool_calls": null
      }
    },
    {
      "finish_reason": "stop",
      "index": 2,
      "logprobs": null,
      "message": {
        "content": "{\n    \"topic_modeling\": \"Comparison, Technology\",\n    \"score_reason\": \"This prompt requires the AI to demonstrate knowledge of two different technologies, compare their features, and explain their distinctions. This task assesses the AI's factual accuracy and proficiency in understanding complex technological concepts.\",\n    \"score_value\": 9\n}",
        "role": "assistant",
        "function_call": null,
        "tool_calls": null
      }
    }
  ],
  "topic_modeling_1": "Technical Comparison",
  "score_reason_1": "This prompt requires the AI to accurately compare and contrast two distinct technologies, OpenCL and CUDA. It assesses the AI's factual accuracy and knowledge of these technologies, as well as its ability to articulate the differences between them.",
  "score_value_1": 9,
  "topic_modeling_2": "Software Comparison",
  "score_reason_2": "This prompt assesses the AI's factual accuracy in distinguishing between two similar but distinct software frameworks.",
  "score_value_2": 8,
  "topic_modeling_3": "Comparison, Technology",
  "score_reason_3": "This prompt requires the AI to demonstrate knowledge of two different technologies, compare their features, and explain their distinctions. This task assesses the AI's factual accuracy and proficiency in understanding complex technological concepts.",
  "score_value_3": 9
}
```
</details>

<details>
<summary>We used the following prompt to generate the responses:</summary>


```markdown
We are interested in understanding how well the following input prompts can evaluate an
AI assistant’s proficiency in problem-solving ability, creativity, or adherence to real-world
facts. Your task is to assess each prompt based on its potential to gauge the AI’s capabilities
effectively in these areas.

For each prompt, carry out the following steps:

1. Topic Modeling: Use two words to describe the task intended.
2. Assess the Potential: Consider how challenging the prompt is, and how well it can
   assess an AI’s problem-solving skills, creativity, or factual accuracy. Briefly explain your
   reasoning.
3. Assign a Score: Assign a score on a scale of 1 to 10, with a higher score representing
   a higher potential to evaluate the AI assistant’s proficiency effectively. Use double square
   brackets to format your scores, like so: [[5]].

Guidelines for Scoring:
• High Score (8-10): Reserved for prompts that are particularly challenging and excellently designed to assess AI proficiency.
• Medium Score (4-7): Given to prompts that have a moderate potential to assess the AI’s
capabilities.
• Low Score (1-3): Allocated to prompts that are either too easy, ambiguous, or do not
adequately assess the AI’s capabilities.

Ensure to critically evaluate each prompt and avoid giving high scores to prompts that are
ambiguous or too straightforward.

The output MUST follow a JSON format:
{
"topic_modeling": "...",
"score_reason": "...",
"score_value": ...
}
```
</details>

<details>
<summary>You can generate your own embeddings</summary>

Note that the provided embeddings are generated using OpenAI's model, which means if you want generate new prompt, you needs an OpenAI developer account ($5 free credit for new signup otherwise needing a credit card). The code used to generate the embeddings is as follows:

```python
import openai
client = openai.OpenAI()
client.embeddings.create(
    model="text-embedding-3-small", input=prompt, extra_body=dict(dimensions=256)
)
```

You are welcomed to use open source models (you can use huggingface on datahub!) to generate the embeddings for the new prompts. A good start would be using huggingface pipeline for embedding generation:

```python
from transformers import pipeline

embedder = pipeline("feature-extraction", model="distilbert-base-uncased")
embeddings = embedder(prompt)
```

You can see more in the [feature extraction pipeline documentation](https://huggingface.co/docs/transformers/v4.37.2/en/main_classes/pipelines#transformers.FeatureExtractionPipeline). It will result in dimension of 768 for each prompt.

</details>

#### Project Tasks

Your tasks will be open ended and feel free to explore the data as you see fit. Overall, you should aim to perform all of the following tasks. We included example questions to consider, but you are expected to come up with your own questions to answer.

- EDA Tasks: Tell us more about the data. What do you see in the data? Come up with questions and answer about them. For example, what are the win-rate of GPT4? What are the most common topics? Do different judges have different preferences?
- Modeling Tasks: Perform some modeling tasks given our ground truth labels. Can you train a logistic regression model to predict the winner given embeddings? How about a K-means clustering model to cluster the questions? Can you use linear regression to predict the hardness score?
- Analysis Tasks: By leveraging the question embeddings, can we find similar questions? How "repeated" is the questions in the dataset? Can you reproduce the Elo score rating for the chatbots?

For EDA task, we expect plots and story telling. For modeling tasks, we expect you to demostrate how the well model works and how to evaluate them. The analysis task is more open ended.

#### Getting Started

To get started, we provide a notebook `nlp-chatbot-starter.ipynb` that demostrate how to load and inspect the data. The project is expected to be open ended!

#### Resources

- [Joey's EDA and Elo rating modeling](https://colab.research.google.com/drive/1KdwokPjirkTmpO_P1WByFNFiqxWQquwH) is a great resource to get started with the EDA. Note that (1) the plot is made with plotly, we recommend you to reproduce the plot with matplotlib or seaborn, and (2) the Elo rating is a good modeling task to reproduce but we expect you to do more than just that (for example, demostrate how Elo rating works and how to calculate it in your report).

- [An intuitive introduction to text embeddings](https://stackoverflow.blog/2023/11/09/an-intuitive-introduction-to-text-embeddings/) is a good resource to understand what is text embeddings and how to use them.

- [Elo rating system](https://en.wikipedia.org/wiki/Elo_rating_system) and [Bradley-Terry model](https://en.wikipedia.org/wiki/Bradley%E2%80%93Terry_model) are essential to model a ranking among the pair wise comparison.

- [Huggingface pipeline](https://huggingface.co/docs/transformers/en/main_classes/pipelines) have many implementations of common NLP task for you to use, including sentiment analysis, summarization, text classification, etc.

- [spaCy](https://spacy.io/usage/spacy-101) is a wonderful library containing classifical NLP tasks like tokenization, lemmatization, etc.

## Group Formation + Research Proposal

The first deliverable of your group project is just to form your group, choose a dataset and submit your research proposal to [this google form](https://forms.gle/KnJPVvbcr6j6wt7GA) by 11:59 pm on 10/06. Along with your research proposal, you are required to briefly explore your chosen dataset and describe it in one paragraph. You may form groups of 2 or 3 people with any Data 200A/200A/200S student. If you are having trouble finding a group, we can assign you to a group if you fill out this [form](https://forms.gle/nPHpmAWgGbjkPYtEA) by 11:59pm on 9/30.

## Checkpoint 1: EDA + Internal Peer Review

The checkpoint is intended to keep you on track to meet your project goals. You will need to submit exploratory data analysis results on Gradescope. This will include submitting both a report of your results so far as well as all code necessary to replicate your results. Your submission should include:

- **Project Introduction and Goals:** Please briefly introduce your project. Think about introducing your project to someone who has a background in data science but does not know the dataset and your research question. This part should not exceed 500 words. Here are some components to help you get started:
  - What is the dataset about? How was the data collected? What are the available features and information? What is the size of the dataset?
  - What questions do you plan to ask about the dataset? Why do we care about such a problem?
  - What is your workflow for the project? Your first step, second step…
  - What are the models you plan to use? Why would the model be a good fit for your project? What are potential pitfalls you could run into?
  - What is your goal for the project? What are the expected deliverables?

- **EDA:** Show the results from your EDA work. You should include:
  - **Data Sampling and Collection**
    - How was the data collected?
    - Was there any potential bias introduced in the sampling process?
  - **Data Cleaning**
    - What type of data are you currently exploring?
    - What is the granularity of the data?
    - What does the distribution of the data look like? Are there any outliers? Are there any missing or invalid entries?
  - **Exploratory Data Analysis**
    - Is there any correlation between the variables you are interested in exploring?
    - How would you cleanly and accurately visualize the relationship among variables?
    - What are your EDA questions? (For example, are there any relationships between A and B? What is the distribution of A?).
    - Do you need to perform data transformations?
  - **Figures(tables, plots, etc.)**
    - Descriptions of your figures. Takeaways from the figures.
    - These figures must be of good quality (i.e. they must include axes, titles, labels, etc) and they must be relevant to your proposed analysis.

- **Other Preliminary Results (optional)**: Please optionally post any other preliminary results here for our information.

## Checkpoint 2: Mandatory Check-In

The purpose of this checkpoint is to ensure you are making progress and on schedule to submit the first draft of the project in 2 weeks time. You will be required to make a one-page document summarizing all of your progress so far, and you will have to bring the document to a one-on-one meeting with a staff member. Please look at the <a href="#checkpoint-2-mandatory-check-in-75">rubric</a> for the checkpoint and what you need to include in the <a href="#final-project-report">Final Project Report</a> when determining what to include in your one-page document; the document should be a brief summary of all your progress so far. The staff member will quickly skim the document and give you guidance on the project as a whole. More details about submitting the one-page document and signing up for the staff member meeting will be announced on Ed soon.

## Final Project Report
The project submission should include the following two components, as well as the YouTube video recording (more information to be announced later).

### [Component 1] Analysis Notebooks

This component includes all the Jupyter Notebook(s) containing all the analyses that you performed on the datasets to support your claims in your write-up. Make sure that all references to datasets are done as `data/[path to data files]`. By running these notebooks, we should be able to replicate all the analysis/figures done in your write-up.

Your analysis notebook(s) should address all of the following components in the data science lifecycle. Please note that a thorough explanation of your thought process and approach is **as important as** your work. Unreadable/uncommented code will lose points. Along with the code for the EDA portion (which also has to be included), we have provided a few additional preliminary questions/tips you can consider for the modelling portion of the project:

  - What are the research questions that you are answering through your analysis? What type of machine learning problem are you investigating?
  - Which model(s) do you use and why?
  - How do you use your data for training and testing?
  - Does your model require hyperparameter tuning? If so, how do you approach it?
  - How do you engineer the features for your model? What are the rationales behind selecting these features?
  - How do you perform cross-validation on your model?
  - What loss metrics are you using to evaluate your model? Why?
  - From a bias-variance tradeoff standpoint, how do you assess the performance of your model? How do you check if it is overfitting?
  - How would you improve your model based on the outcome?
  - Are there any further extensions to your model that would be worth exploring?


### [Component 2] Project Write-Up

This is a single PDF that summarizes your workflow and what you have learned. It should be structured as a research paper and include a title, list of authors, abstract, introduction, description of data, methodology, summary of results, discussion, conclusion, and references. Make sure to number figures and tables, include informative captions and ensure you include the provenance of the figures in the main narrative. We encourage you to render the PDF using LaTeX, but we will not be able to provide assistance with LaTeX-related issues.

Specifically, you should ensure you address the following in the narrative:

* Clearly state the research questions and why they are interesting and important.
* Introduction: ensure you include a brief survey of related work on the topic(s) of your analysis. Be sure to reference current approaches/research in the context of your project, as well as how your project differs from or complements existing research. You must cite all the references you discuss in this section.
* Description of data: ensure you outline the summary of the data and how the data was prepared for the modeling phase (summarizing your EDA work). If applicable, descriptions of additional datasets that you gathered to support your analysis may also be included.
* Methodology: carefully describe the methods/models you use and why they are appropriate for answering your research questions. You must include a detailed description of how modeling is done in your project, including inference or prediction methods used, feature engineering and regularization if applicable, and cross-validation or test data as appropriate for model selection and evaluation. <!-- You may also include interesting findings involving your datasets. -->
* Summary of results: analyze your findings in relation to your research question(s). Include/reference visualizations and specific results. Discuss any interesting findings from your analysis. You are encouraged to compare the results using different inference or prediction methods (e.g. linear regression, logistic regression, or classification and regression trees). Can you explain why some methods performed better than others?
* Discussion: evaluate your approach and discuss any limitations of the methods you used. Also, briefly describe any surprising discoveries and whether there are any interesting extensions to your analysis.

The narrative PDF should include figures sparingly to support specific claims. It can include a few runnable code components, but it should not have large amounts of code. The length of the report should be 8 ± 2 pages when it is printed as a PDF, excluding figures and code.

Tip: if you need to write a large amount of LaTeX on markdown, you may want to use the `%%latex` cell magic. However, we also encourage you to explore [Overleaf](https://www.overleaf.com) for easily writing clean LaTeX documents.

Please submit everything as a zip file to the final report submission portal on Gradescope. Please make sure the folder in the zip file has the following structure:

```
[your studentIDs joined by _]/
    data/[all datasets used]
    analysis/[analysis notebooks]
    narrative/[narrative PDF]
    figures/[figures included in the narrative PDF]
```

Please use student IDs joined by `_` as the name for the top-level directory. The analysis notebooks must be runnable within this directory structure. If the narrative PDF includes any figures that are created in the analysis notebooks, the figures should be saved to `figures/` by the analysis notebooks.

## Rubrics
This section includes a rubric for how different project deliverables are going to be graded. This section will be updated as we get further along the project timeline.

### Group formation + Research Proposal (5%)
- One paragraph description of the data that will be used in the project (1.5%).
- List of research questions and their alignment with the given datasets (1.5%).
- Forming teams by the deadline (2%).

### Checkpoint 1: EDA + Internal Peer Review (10%)
- Project Introduction and Goals (0.5%).
- Data Sampling and Collection (0.5%).
- Data Cleaning (3%).
- Exploratory Data Analysis (3%).
- Figures (tables, plots, etc.) (2.5%).
- Internal Peer Review (0.5%).

### Checkpoint 2: Mandatory Check-In (7.5%)
- Research Questions (1.5%).
- Feature Engineering (2%).
- Modelling Approaches (3%).
- Preliminary Results (1%).

<!---

### Checkpoint Rubric

See the checkpoint description [here](#checkpoint).

| Criterion | Points |
| --- | --- |
| Project Introduction and Goals | 4 |
| EDA 1 | 3 |
| EDA 2 | 3 |
| Other Preliminary Results (optional) | 0 |

### Internal Peer Review

The internal peer review is a simple google form checking if each member of the group is contributing to the project and how the tasks are distributed among members. This is graded on completion.

### External Peer Review

Each group will peer review the projects from another group. The review will be graded by staff out of a total of 5 points. Each review should include the following components:

1. (1 point) A summary of the report. The summary should address at least the following:
  - What research question does the group propose? Why is it important?
  - How does the dataset relate to the research question?
  - What data modeling/inference techniques do the group primarily use to gain insights into their research question? Why are these techniques suitable for the task?
  - What are the next steps a researcher can take if they want to investigate the question further based off the work in the project?

2. (4 points, 2 per component) An evaluation of the report based on the Data Science Lifecycle. The review should include at least **one strong point and one suggestion for improvement** for each of the following components in the project:
  - Data collection and sampling
  - Data cleaning
  - Exploratory data analysis (data wrangling, visualization, etc.)
  - Data modeling (feature engineering, selection of the model, and evaluation of the model's performance, etc.)
  - Inference (do the results from the model sufficiently support the conclusion within the report?)

The external peer review is also a great chance to learn from other people's work and reflect on the work of your own.

### Final Report: Analysis Notebook

| Criterion                                             | Points|
|-------------------------------------------------------|-------|
| Code readability and documentation                    | 5     |
| Proper and sufficient utilization of Python libraries | 5     |
| Overall code quality                                  | 3     |
| Replicability of the results                          | 7     |
| **Total**                                             | **20**|

### Final Report: Project Writeup

| Criterion                                                              | Points|
|------------------------------------------------------------------------|-------|
| Introduction, motivation, and presentation of the research question(s) | 3     |
| Exploratory data analysis                                              | 5     |
| Modeling and inference techniques                                      | 7     |
| Analysis of results                                                    | 7     |
| Implementation of peer review feedback                                 | 3     |
| Discussion of potential societal impacts and/or ethical concerns       | 2     |
| Overall clarity and structure of the report                            | 3     |
| **Total**                                                              | **30**|
-->

## Extra Resources: Causal Inference

When studying the relationship between datasets, you might want to consult the following references on causality vs. correlation. Oftentimes, it is tempting to make claims about causal relationships when there is not enough evidence from the data to support such claims. Please review the following references, or other reputable references that you find on the topic to familiarize yourself with relevant concepts and methods.

* [Data 102  Data, Inference, and Decisions Spring 2020: Lecture 13: Causal Inference I. Moritz Hardt.](https://data102.org/sp20/assets/notes/notes13.pdf)
* [Hernán MA, Robins JM (2020). Causal Inference: What If. Boca Raton: Chapman & Hall/CRC.](https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/)
* [Advanced Data Analysis from an Elementary Point of View by Cosma Rohilla Shalizi](https://www.stat.cmu.edu/~cshalizi/ADAfaEPoV/)
