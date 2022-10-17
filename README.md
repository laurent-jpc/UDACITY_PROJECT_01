PROJET/PURPOSE:

UDACITY PROJECT 01 - Write a Data Science Blog Post


TITLE:

Go through COVID-19 during hospitalizations in France: attention fully focused on patients.


PROJECT MOTIVATION

Through this project I would make a first step in the data science approach. In addition, I was requested to use professional tools to transmit this work which is new for me. It will improve my capacity to communicate my project to my colleagues in a proper way.
In parallel, I would also have my own vie on Covid-198 figures since we heard a lot about this topic since a long time now, but I did not access to the real figures directly from hospitals. Which is now done!


DESCRIPTION:

Based on data provided by the hospitals about Covid-19 patients hospitalized in France, 
I decided to analyze these data for reporting result in my Data Science Blog Post.
Thus, I provide some stats related to admission, hospitalization and discharge of COVID-19 (virus SARS-CoV-2) patients in French hospital a bounce of September 2022.


PROCESSING AND ANALYSIS:

Business Understanding
    With new increase of the COVID-19 patients in France in September 2022, I'd like to get a view on the path of patients hospitalized for COVID-19 and on daily feedback of reception of these patients by the hospitals.
	
	Question 1: What are the most missing data provided by hospitals about Covid-19 patients ?	
	
	Question 2: Which categories have the most effect on the linear model to assess mortality due to Covid-19 ?
	
	Question 3.1: What is the proportion of hospitalized Covid-19 patients which go in critical care ?
	Question 3.2: According to the result of the preceding block that raises the importance of the gender for the model,
				  what is the proportion of female and male Covid-19 patients that finally died due to Covid-19 ?

	
Data Understanding
    Access and Explore : data are recorded in a csv file provided with the python script. It was zipped to comply with the limit of uploading 30Mo-limit of GITHUB.
						 Path of the csv data file is written in the python script (refer to the sub-function "get_input_filepath").
						 The csv data file is read and transpose in dataframe via the pandas python library, with ';' as separator.
						 
Prepare Data
    Clean : 
	- For question 1: there is not clean; the way to answer the question consists in monitoring 'na' values of the full dataframe.
	- For questions 2 and 3: cleaning of data was realized in several steps:
							 - Managing dummy parameters by adding related categorical parameters
							 - Remove row and column when all values are missing
							 - Infinite values are replaced by Nan
							 - Replace Nan values in float and int column by mean value
	
Data Modeling (Optional)
    Fit model : I established a sklearn linear model that assess mortality of Covid-19 patients according to other parameters.
			    I selected a set of parameters, including with result of question 1, that allows getting the best R2 score with few initial entries.
				This model is established with 70% of the dataset
    validate the model
				Validation of the model is established with 30% of the dataset.
				Since the model is based on a linear regression, I decided to use sklearn R2 score as metrics to validate the model:
				- 0.976 on train data
				- 0.976 on test data
				Best possible score is 1.0. So my model initialy based (before dummy) on 5 parameters has a satisfactory R2 score.
	
Evaluation
    Question 1 -> Part 3 (presented at the end because it concerned the hospitals' capacity.
        I see that categories 'Nb_Quotidien_Retour_a_Domicile', 'Nb_Quotidien_Deces',
		  'Nb_Quotidien_Admis_Reanimation' and 'Nb_Quotidien_Admis_Hospitalisation'
		  have more than 66% of missing data. Hostpitals can't or don't want fulfil these information.
		  In addition, categories 'autres', 'SSR_USLD' and 'HospConv' reach a bit less than 40%.
		  Maybe, I would have a better model using other remaining data which have less than 1% of missing data. 
    Question 2 -> Finally not presented because result is not relevant considering the few parameters to assess the mortality rate.
        Linear model's weight coefficients show that gender of patients is the first category of the model (mortality), before department code.
    Question 3 -> Part 1 and Part 2
        Concerning Covi-19 patients, when the 5%-most critical cases are spread:
			- 95% of patients had a 70% chance to avoid intensive care. This decreases to 50% considering 99.7% of thez patients.
			- 95% of patients had a 97.6% chance to survive the Covid-19 for female and 98.1% for mal. This increases to 99.9% of patients while considering 99.7% of the whole patients.
	These answers are noted at the end of every concerned part of the code, to get the code's ouput and my conclusion in a single view.
	
	Resulting figures have can be interpreted in the context of the three questions.


VERSION:

ID: 1.1.0

This version brings following changes from 1.0.0 to 1.1.0:
- Split the code with markdowns
- In last version, I used a variable to work on different parts of the dataframe and process specific analysis.
  Now i've sequenced these actions such that the usr do not haveto modify a script's variable.
- New sub-functions for replacing existing code lines, essentially for debug mode
- Format values of variables __version__ changed
- New variable __date__
- Variable debug replaced by __debug_script__ for a use along all markdows.
- Implementation of the pycodestyle's rules, with some reported and commented exceptions.
  For instance, I know that I should use 'try: ... except' without specifying expected errors and without dealing with potential errors before the 'try ... except'.
  I would do it if I have more time.
- Addition of comments on results at the end of every part of the code where analysis's result is expected.
- Implement Docstrings under the required format at beginning of every function.

			
			
PUBLIC RELEASE:

You can find the published results here: https://medium.com/@laurent.jp.costa/some-stats-related-to-covid-19-hospitalizations-in-france-at-bounce-of-september-2022-f8ff6807d3c0


ENVIRONMENT:

Microsoft Office 2013
Visual Studio Code 1.61.2
Python 3.7.8 64-bit (system)
Specific libraries: numpy, pandas, sklearn, pycodestyle, flake8 (see the file requirements.txt)


REPOSITORY’S FILES:

File “README.md”
File “donnees-hospitalieres-covid-19-dep-france.zip” – This a csv file providing hospital data file gathered and provided by opendatasoft.com website.
File "requirements.txt" - This script works with some librairies; to install these librairies you will need to execute: pip install -r requirements.txt
File “project_01_main_v1.1.0.ipynb” – Jupyter notebook file containing python script for reading, modeling and analyze data.
In the python script, change boolean value of the variable 'use_full_data_set' to get appropriate observation results: False for items 1 and 2 ; True for item 3. In the python script, change string value of the variable 'filepath' in accordance with your environment.


DATA SOURCE:

- Name: data.opendatasoft.com
- Link: https://data.opendatasoft.com/explore/dataset/donnees-hospitalieres-covid-19-dep-france%40public/export/?flg=fr&disjunctive.countrycode_iso_3166_1_alpha3&disjunctive.nom_dep_min, extracted September 26st, 2022 for a report of the situation at the same date


ACKNOWLEDGEMENTS:

- Dataset credit: Santé Publique France


LEGAL / LICENSE:

- License: Licence Ouverte v2.0
- Reuse and exploitation of source data: https://www.etalab.gouv.fr/wp-content/uploads/2018/11/open-licence.pdf
