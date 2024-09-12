This repository contains supporting materials for the paper "What Properties Affect Boolean Formula Comprehension in Formal Specifications?"

It contains the following folder structure and files:


Experiment Design:

Consent.pdf - the consent form of the experiment platform
Instructions.pdf - the instructions page of the experiment platform
formula_corpus.csv - the corpus of formulas filtered from the Spectra specifications, divided by the criteria in Section IV.A


Experiment Results:

raw_data.csv - the results and the demographic data of 181 participants
category_results.csv - the statistical data and analysis of each test category (based on the raw data)
formula_results.csv - the statistical data of each formula pair (based on the raw data)


Refactoring Procedure:

refactoring_procedure_data.csv - the data of the refactoring procedure execution on the formula corpus, including running times, the refactored formula, and reading complexity scores before and after

refactoring_procedure.jar - to execute the jar, run `java -jar refactoring_procedure.jar '[FORMULA] [NUM_RESULTS]'.
The formula syntax accepts the following operators: "&", "|", "->", "<->", "!". The top-level formula as well as all subformulas must be wrapped in parentheses. In a Windows environment, double quotation marks should be used instead of single quotation marks as in Unix environments
	
Example command:

`java -jar refactoring_procedure.jar '((!a & !b & !c)->d)' 3`

The output is NUM_RESULTS formulas sorted by the reading complexity score in ascending order:

`[(a|b|c|d), !(!a&!b&!c&!d), (!d->(a|b|c))]`


formula_score_calc.jar - prints the reading complexity score of a formula

Example command:

`java -jar formula_score_calc.jar '((!a & !b & !c)->d)'`

With output:

`21.69`
