# starbucks_offer_success_classification
Machine Learning project which predicts success of offers send by Starbucks app.

### Table of Contents

1. [Installation](#installation)
2. [Project Description](#description)
3. [Project Motivation](#motivation)
4. [File Descriptions](#files)
5. [Results](#results)
6. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

To execute the project it's recommended to run the Anaconda distribution of Python. The code should run with no issues using Python versions 3.*.

## Project Description <a name="description"></a>

### Business Understanding

Starbucks is an American coffeehouse chain inspired by Italian Cafe' culture. They sell drinks, food and merchandise. The Starbucks app is a customer loyalty tool, which offers queue-free online ordering, a reward program and discounts. This analysis should investigate how to find best matching offers for different groups of customers.  

### Data Understanding

This analysis project uses simulated data provided by Starbucks. Key objects are customers, offers and customer activities, which are provided in separated files. It's possible to join the data via customer and offer ids. The customer and offer files consists of one row per ID and provides metadata about the entities. The customer activity file (transcript.json) could contain several entries per customer and offer. It logs following events: offer received, offer viewed, offer completed and transactions.

Overview of the data schema and its variables:

 portfolio.json<br/>
 id (string) - offer id<br/>
 offer_type (string) - type of offer ie BOGO, discount, informational<br/>
 difficulty (int) - minimum required spend to complete an offer<br/>
 reward (int) - reward given for completing an offer<br/>
 duration (int) - time for offer to be open, in days<br/>
 channels (list of strings)<br/>

 profile.json<br/>
 age (int) - age of the customer<br/>
 became_member_on (int) - date when customer created an app account<br/>
 gender (str) - gender of the customer<br/>
 id (str) - customer id<br/>
 income (float) - customer's income<br/>

 transcript.json<br/>
 event (str) - record description (ie transaction, offer received, offer viewed, etc.)<br/>
 person (str) - customer id<br/>
 time (int) - time in hours since start of test. The data begins at time t=0<br/>
 value - (dict of strings) - either an offer id or transaction amount depending on the record<br/>

Files in this repository:<br/>

 Starbucks_Capstone_notebook.ipynb - Jupyter Notebook with data analysis<br/>
 rfc.sav - exported Random Forrest classifier<br/>
 gradboost.sav - exported Gradient Boosted Classifier<br/>

### Data Preparation and Modeling

To analyze offer completion and make predictions about it, the files have to be merged (via offer and person id). There are some tricky cases where customers received an offer and completed it by fulfilling all conditions without viewing the offer. This has to be considered during the data preparation process. The value column found in transcript file is a dictionary, which has to be split for further processing. Customer data contains some missing values, which should be removed.

### Result Evaluation

The developed model should be helpful to increase offer completion rates. With an accuracy of 72% it is a big advantage over sending offers of all types to all customers.

## Project Motivation<a name="motivation"></a>

Predicting offer completion for customers was an exciting and ambitious capstone project in my Udacity Data Science Nanodegree program.

## File Descriptions <a name="files"></a>

The python code can be found in a Jupyter Notebook. The analysis process is documented with Markdown cells, comments and docstrings.

## Results<a name="results"></a>

The main findings of the code can be found at the post available [here](https://medium.com/@ewarest/starbucks-gonna-make-an-offer-you-cant-refuse-ba5971dec2a0).

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Thanks to Starbucks for providing the dataset for Udacity Nanodegree program.
