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

All the datasets provided by us can be found inside the following link on Google Drive:

<p align="center">
<a href="https://drive.google.com/drive/folders/1GiQJ-wu_ZKr_9FZGqyY-aBHahkDObdAr?usp=drive_link">Graduate Project Datasets Google Drive</a>
</p>

If you wish to work on Datahub, we've provided some instructions on how to move the data from Google Drive onto Datahub. However, your Datahub kernel can often only manage 2GB of memory at maximum. Given this limitation (and the size of most datasets), we recommend instead using Google Drive + Google Colaboratory. If you instead wish to work on the project locally, you can also download the files containing the datasets for each topic.

#### **How to Pull Data from Google Drive directly onto Datahub**
{:.no_toc}

1. _Get the Google Drive ID of the file_. To do this, first get the URL of the file. You can do this by right-clicking on the file in Google Drive and pressing 'Share -> Copy Link'. Once you have the URL, you can find the ID by looking for the set of characters after the /d/ in the URL. For example, in the following URL: `https://drive.google.com/file/d/16-4O_lJGioPC5G9il4vR_XrCgJ3J9_zK/view?usp=sharing`, the Google Drive ID would be `16-4O_lJGioPC5G9il4vR_XrCgJ3J9_zK`.
2. _Download the data_. Once you have the Google Drive ID of the file, you can use the `utils.py` file inside the `grad_proj` directory on your Datahub. This file has a number of useful functions for downloading data. You'll want to use `fetch_and_cache_gdrive`. You will call the function in a notebook. The function takes in two arguments: **(1) Google Drive ID** that you got in the previous step, and **(2) name of the file**. Calling the function will generate a `data` folder and place the file into that folder, using the name you came up with as the second argument of the function.

Hopefully, the above steps help you to access the data on Google Drive. There are other ways to move the data onto Datahub. Consider looking into [`gdown`](https://github.com/wkentaro/gdown) or just downloading the data from Google Drive and uploading it to Datahub manually.

Take a look at the other functions in `utils.py` if you'd like to use other data sources to supplement your project. 

### Topic 1: Computer Vision
In disaster situations, it is important for emergency response efforts to have access to quick and accurate information about an area in order to respond effectively. This project will explore how data science techniques can be useful for such efforts.

#### Sections
This document contains the following sections:
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

##### Exploratory Data Analysis
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
### Topic 2: Climate and the Environment

#### Dataset A: General Measurements and Statistics <a name="2-a"></a>
{:.no_toc}

This dataset contains some general statistics and measurements of various aspects of the climate and the environment. You can access all the data within the `Topic 2/Dataset A` directory on Google Drive. It includes the following reports:

- `daily_global_weather_2020.csv` contains data on daily temperature and precipitation measurements. To learn how to use the data from this file, please read the following section on the first report.
- `us_greenhouse_gas_emissions_direct_emitter_facilities.csv` and `us_greenhouse_gas_emission_direct_emitter_gas_type.csv` contain data reported by EPA (Environment Protection Agency) on greenhouse gas emissions, detailing the specific types of gas reported by facilities and general information about the facilities themselves. The dataset is made available through EPA's [GHGRP (Greenhouse Gas Reporting Program)](https://www.epa.gov/ghgreporting).
- `us_air_quality_measures.csv` contains data from the EPA's AQS (Air Quality System) that measures air quality on a county level from approximately 4000 monitoring stations around the country. ([source](https://data.cdc.gov/Environmental-Health-Toxicology/Air-Quality-Measures-on-the-National-Environmental/cjae-szjv))
- `aqi_data` contains more data from the EPA from a number of sites across a multitude of different metrics. ([source](https://aqs.epa.gov/aqsweb/airdata/download_files.html))

The following subsection contains more details on how to work with the first report on global daily temperature and precipitation:

The first report on daily temperature and precipitation is measured by weather stations in the [Global Historical Climatology Network](https://www.ncdc.noaa.gov/data-access/land-based-station-data/land-based-datasets/global-historical-climatology-network-ghcn) for January to December 2020.

The data in `daily_global_weather_2020.csv` is derived from the source file at [https://www1.ncdc.noaa.gov/pub/data/ghcn/daily/by_year/2020.csv.gz](https://www1.ncdc.noaa.gov/pub/data/ghcn/daily/by_year/2020.csv.gz).

To help you get started with a dataset of manageable size, we have preprocessed the GHCN dataset to include only the average temperature and precipitation measurements from stations that have both measurements. Each row in the preprocessed dataset contains both the average temperature and precipitation measurements for a given station on a given date.

If you wish to explore the climate data for a different year, you can use the `GHCN_data_preprocessing.ipynb` notebook to download and perform the preprocessing described above. Please be advised that depending on the dataset size for a given year, `GHCN_data_preprocessing.ipynb` may not run on DataHub. 

The data contains only the (latitude, longitude) coordinates for the weather stations. To map the coordinates to geographical locations, the [reverse-geocoder](https://github.com/thampiman/reverse-geocoder) package mentioned in the [References](#coordinates) section might be helpful.

#### Dataset B: Biodiversity in the Ecosystem
{:.no_toc}

This dataset contains studies focused specifically on the impact of environmental and climate changes on biodiversity and the local ecosystems. You can access all the data within the `Topic 2/Dataset B` directory on Google Drive. It includes the following reports:

- `bioCON_plant_diversity.csv` contains data collected as part of an ecological experiment, BioCON (Biodiversity, CO2, and Nitrogen), that started in 1997 and focused on studying biodiversity within the plant species at Cedar Creek Ecosystem Science Preserve. ([documentation](https://search.dataone.org/view/https%3A%2F%2Fpasta.lternet.edu%2Fpackage%2Fmetadata%2Feml%2Fknb-lter-cdr%2F339%2F9))
- `plant_pollinator_diversity_set1.csv` and `plant_pollinator_diversity_set2.csv` contain ecological data collected from a long-term observation study from 2011 to 2018 that focuses on plant-pollinator interaction and its impact on local biodiversity. ([documentation](https://search.dataone.org/view/https%3A%2F%2Fpasta.lternet.edu%2Fpackage%2Fmetadata%2Feml%2Fknb-lter-and%2F5216%2F6))
- `national_parks_biodiversity_parks.csv` and `national_parks_biodiversity_species.csv` contain data published by the National Park Service on animal and plant species identified in individual national parks.

### Topic 3: Recommender Systems <a name="tech"></a>

<!--#### Dataset A: Space Exploration
{:.no_toc}

This dataset contains a set of reports from pioneering researches that explore the outer space. Much of the data from these studies have provided a rich foundation for a variety of large-scale research projects that explore widely discussed topics such as habitable exoplanets or search for extraterrestrial life.

You can access all the data within the `Topic 3/Dataset A` directory on Google Drive. It includes the following reports:

- `kepler_exoplanet_search.csv` contains data collected by NASA from the Kepler Space Observatory as part of a long-term study on finding habitable exoplanets from over 10,000 candidates. ([source](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=koi))
- `kelper_planetary_system_composite.csv` contains data collected by NASA from the Kelper Space Observatory as part of an ongoing study that tabulates all confirmed planetary systems outside the solar system. You are encouraged to use the composite data in conjunction with the exoplanet search results above. ([source](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PSCompPars))
- `nasa_neows.csv` contains data collected from NASA's [NeoWs (Near Earth Object Web Service)](https://neowise.ipac.caltech.edu/) that collects information on near earth asteroids.-->


A recommender system is an information filtering system that focuses on predicting the preference a user would give to an item by predicting its rank; it is used in a variety of areas, such as search engines, online shopping platforms, etc. This dataset contains a set of reports on various tools using a recommender system.

You can access all the data within the `Topic 3/Dataset A` through the `Topic 3/Dataset C`  directory on Google Drive.

#### Dataset A: Fitness Recommendations
{:.no_toc}

These datasets consist of user sports records collected from Endomondo. They include a rich variety of sequential sensor data, such as metrics like heart rate, speed, GPS coordinates. Additionally, the datasets contain information about the type of sport, user gender, and weather conditions, which encompass temperature and humidity.

- Relevant data can be found in `Topic 3/Dataset A` on the Google Drive. You may also visit the [main page](https://sites.google.com/eng.ucsd.edu/fitrec-project/home) for documentation and links to download the dataset.

#### Dataset B: Amazon Recommendations
{:.no_toc}

These datasets comprise Amazon reviews, which encompass ratings, textual content, and helpfulness votes for a wide variety of Amazon categories, such as fashion, electronics, and pet supplies. They also contain product metadata, including descriptions, category information, price, brand, and image features.

- Instructions on how to access the data is located in `Topic 3/Dataset B` on the Google Drive. You may also directly visit the [main page](https://nijianmo.github.io/amazon/index.html), which includes general information about the dataset, such as metadata and categories, as well as the dataset request process. 

#### Dataset C: Application Usage Recommendation
{:.no_toc}

The frappe dataset contains a context-aware app usage log consisting of 96,203 entries by 957 users for 4,082 apps used in various contexts. These contexts include factors such as time of day, country, number of downloads, and cost.

- `frappe.csv` and `meta.csv` contain data on mobile app usage for users in various contexts. For general information about the dataset, please refer to `frappe_README.txt` and `stats.ipynb`.

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
