<p align="center">
  <img width="400" height="269" src="https://github.com/gabriela6/legal-clause-classification/blob/main/images/law_and_technology.jpg">
</p>
Source: [1]

# legal-clause-classification
The goal of the project is to create a binary neural network classifier able to detect abusive clauses in legal contracts. Data comes from the UOKiK (The Office of Competition and Consumer Protection) competition “Development of software using AI for text analysis of contract templates used in consumer trade in terms of searching for prohibited clauses in contract templates in B2C relation”, which was organised as a realisation of project "Artificial Intelligence for Consumer Protection Empowerment" https://konkursy.govtech.gov.pl/start/postepowanie/137. 

A project is being done for a course “Natural Language Processing” at Interdisciplinary Centre for Mathematical and Computational Modelling University of Warsaw. I haven’t participated in the competition.
## Competition goal
Currently UOKiK checks contracts for abusive clauses only after reports. Moreover, it is time consuming and has to be done by specialist. The Office plans, that with automated system for clauses classification it will be able to actively monitor contract templates and remove ones containing abusive clauses from the internet. 
## Dataset structure 
Training dataset contains 4284 clauses with labels: 2338 clauses with label “BEZPIECZNE_POSTANOWIENIE_UMOWNE” (Safe contract term) and  1946 clauses with label “KLAUZULA_ABUZYWNA” (abusive clause). Dataset is a csv file with columns “text” and “classes”. Polish is a language of the dataset. 

Test dataset contains 3453 clauses with labels: 2333 clauses with label “BEZPIECZNE_POSTANOWIENIE_UMOWNE” (Safe contract term) and 1120 clauses with label “KLAUZULA_ABUZYWNA” (abusive clause).
## Preprocessing
After cleaning, text was lemmatized and vectorized with the pretrained spacy polish pipeline "pl_core_news_md". 
## Model Structure
Model has a structure of a recurrent neural network with LSTM layer. An Adam Optimizer has been chosen as an optimization algorithm. Binary Crossentropy was used as loss function.
| Layer (type) | Output Shape | Param | 
| --- | --- |--- |
| lstm (LSTM)|(None, 300)| 721200 |
| dense (Dense)|(None, 1)|  301 |

 Total params: 721,501
## Model evaluation
The model achieved F-score of 69,6 % and balanced accuracy of 77,8%. Probably a larger dataset or a different network architecture is necessary to achieve better results. 
## Used external libraries
pandas, NumPy, Matplotlib, scikit-learn, Keras, spaCy, seaborn
## Sources
[1] https://www.flickr.com/photos/arselectronica/50224297163 Licence: https://creativecommons.org/licenses/by-nc-nd/2.0/
[2] https://www.intel.com/content/www/us/en/developer/learn/course-natural-language-processing.html
[3] https://konkursy.govtech.gov.pl/start/postepowanie/137
