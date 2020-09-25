# Automated-Identification-of-Bias-Inducing-Words-in-News-Articles

## Description of the attached data files (only data files created during the thesis project are attached, external files aren't attached)

## Description of the attached scripts (data files attached: +, not attached: -)
### 1.1_Survey_results_processing.ipynb
In this script, we:
- assemble the row survey data into a dataset for further media bias analysis,
- retrieve descriptive statistics of the assembled dataset.

To run this script, the following data files are needed:
- annotations_final_notempty.xlsx
- sentences_final.xlsx
- biased_words_analysis.xlsx
- articles.xlsx
- labeled_dataset.xlsx
- annotators.csv

### 1.2_Annotations_analysis.ipynb
In this script, we:
- explore the annotations,
- explore the perception of bias.

To run this script, the following data files are needed (attached):
- labeled_dataset.xlsx
- annotations_final_notempty.xlsx
- results_bias.xlsx

### 2.1_Word_emb_for_biased_corpora.ipynb
In this script, we:
- train word embeddings for HuffPost and Breitbart
- extract seed biased words from the words close to the words describing contentious topics

To run this script, the following data files are needed:
- left_news_dates.csv (-)
- right_news_dates.csv (-)
- wordsim353.tsv (-)
- men.txt (-)
- questions-words.txt (-)

Saved models:
- huff_simp_bi_trigr10.model (+)
- breitbart10.model (+)

### 2.2_Bias_lexicon_creation.ipynb
In this script, we create the bias words lexicon semi-automatically

To run this script, the following data files are needed:
- GoogleNews-vectors-negative300.bin (-)
- wordsim353.tsv (-)
- men.txt (-)
- questions-words.txt (-)
- seed_biased_words.xlsx (+)

### 3.1_Features_engineering.ipynb
In this script, we:
- pre-process the sentences,
- create features,
- prepare data for further ML training (e.g., one-hot encoding, etc.)

To run this script, the following data files are needed:
- labeled_dataset.xlsx

Dictionaries needed to run the code (only biased lexicon is attached): 
- details in the script

### 3.2_Features_analysis.ipynb
In this script, we visually analyze the collected features

To run this script, the following data files are needed:
- dt_final.xlsx (attached)

### 4.1_ML_algorithm_selection.ipynb
In this script, we train many "quick and dirty" classifiers with default parameters and choose the best one for further optimization.

To run this script, the following data files are needed:
- dt_final.xlsx (attached)

### 4.2_ML_XGBoost_optimization.ipynb
In this script, we:
- evaluate baselines,
- conduct a grid search for XGBoost to find optimal hyper-parameters,
- evaluate the model,
- evaluate features importance

To run this script, the following data files are needed:
- dt_final.xlsx (+)

Saved models:
- xgboost_tuned_weighted.model (+)

### 4.3_ML_features_selection.ipynb
In this script, we remove different groups of features from training to see when the performance decreases

To run this script, the following data files are needed:
- dt_final.xlsx (+)

Saved models:
- xgboost_no_enrichm.model (+)
- xgboost_no_tfidf.model (+)
- xgboost_no_lex.model (+)
- xgboost_no_liwc.model (+)
- xgboost_no_bias_lex.model (+)
- xgboost_no_context.model (+)
