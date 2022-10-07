# UDACITY_PROJECT_01
UDACITY PROJECT 01

TITLE

Some stats related to COVID-19 hospitalizations in France at bounce of September 2022.


PURPOSE

With new increase of the COVID-19 patients in France in September 2022, I'd like to get a view on the path of patients hospitalized for COVID-19 and daily feedback of reception of these patients by the hospital.


DESCRIPTION

Some stats related to admission, hospitalization and discharge of COVID-19 (virus SARS-CoV-2) patients in French hospital.


RESULT SUMMARY

The observations of data raise that:
1 - Transfer rate from hospitalized patients to critical care reaches 50% considering 99.7% of inputs with more than 10 patients hospitalized. It very rare cases, it can reach 80% (max).
2 - The gender of the patients is a key factor in the rate of mortality due to COVID-19.
3 - All hospitals do not have or take time to provide daily data.


PUBLIC RELEASE

You can find the published results here: https://medium.com/@laurent.jp.costa/some-stats-related-to-covid-19-hospitalizations-in-france-at-bounce-of-september-2022-f8ff6807d3c0


ENVIRONMENT
-	Microsoft Office 2013
-	Visual Studio Code 1.61.2
-	Python 3.7.8 64-bit (system)
-	Specific libraries: numpy, pandas, sklearn


DATA SOURCE

link: https://data.opendatasoft.com/explore/dataset/donnees-hospitalieres-covid-19-dep-france%40public/export/?flg=fr&disjunctive.countrycode_iso_3166_1_alpha3&disjunctive.nom_dep_min
extraction: extracted September 26st, 2022 for a report of the situation at the same date


REPOSITORY’S FILES

- File “README.md”
-	File “donnees-hospitalieres-covid-19-dep-france.zip” – This is a csv file providing hospital data file gathered and provided by opendatasoft.com website. It was zipped for the import (limit at 25Mo).
-	File “project_01_main_v20220927.ipynb” – Jupyter notebook file containing python script for reading, modeling and analyze data.

In the python script, change boolean value of the variable 'use_full_data_set' to get appropriate observation results: False for items 1 and 2 ; True for item 3.
In the python script, change string value of the variable 'filepath' in accordance with your environment.


LEGAL

Reuse and exploitation of source data: https://www.etalab.gouv.fr/wp-content/uploads/2018/11/open-licence.pdf
