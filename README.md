# Description2Code dataset and (very messy) scrapers

Description2Code is dataset of ~5300 programming challenges scraped from Codechef and CodeForces in 2016.

Link to download dataset:
https://docs.google.com/uc?id=0Bz3fihKG133ceWNFQTQ5S0xhZUk&export=download

Story of dataset creation:
https://github.com/openai/requests-for-research/pull/5

Very messy code that was used for scraping codechef, codeforces, hackerearth, & topcoder in 2016 is located in `description2code/scrapers` folder. Hackerearth & Topcoder programming challenge data was abandoned for reason I can't remember.

# Notes on usage of dataset that download link contains

## CodeChef
* Contains curriculum of problems increasing as easy < medium < hard < harder < hardest
* External folder contains 2070 problems of varying difficulty

## CodeForces
* Problem's difficulty relative to other problems in individual competition is indicated by suffix letter on end of folder ( A < B < C < D < E < F < G < I < J ); individual competition is signified by prefix number at start of folder
* '_tags.txt' contains list of which types of algorithmic techniques are need to solve each problem; could be used to benchmark which types of problems your model is/isn't capable of solving or possibly as a supervision signal.
* samples folders contain several input/output samples that could be used to reward model when it generates code that correctly processes sample input into sample output. Several input/output examples are contained in each samples folder to prevent model from overfitting to generated code that could only correctly process a single sample input to sample output.  
* 'description_annotated.txt' is version of description that annotates tokens (with dagger (U+2020) and double_dagger (U+2021) at beginning and end of token(s) respectively) that are meant to be program variables.

## General Usage
* description folder contains input for model; solutions_* (c++ or python depending on what you want to train on) contains target output for model.
* Use Example Input(s)/Output(s) near bottom of 'description.txt' to test whether generated code is correct.
* Train on multiple solutions provided for each problem to help your model generalize.
* Use several sample input/output from samples folder to reward model for generating code that passes all possible test cases.
* versions of collected solution source codes are Python 2 and C++ 4.3.2



## License
I don't "own" the data scraped. Codechef and CodeForces or their users or something technically own it (or maybe they don't; idk). I don't know what the legal_preferences/data_licenses of Codechef and CodeForces and their users are.
 
I'm fine with you using this dataset and scraping code however you want.
