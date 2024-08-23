# Gender-Bias-Footprint
  The typology of people according to the degree of exposure to gender prejudice.
 ---
 ## Discription
  This project is aimed at developing a machine learning model that can classify people according to their degree of commitment to gender biases, as well as select issues that are classified more effectively. Using a dataset containing answers to the test questions compiled by me, the model will be trained to determine how much a person is prone to/free from gender bias and stereotypes.
 ## DATA
 
<u>__[Link](https://docs.google.com/forms/d/e/1FAIpQLScx4fRH2dM74Nvb3Fl5_AZqwAxiVc8XD3OmDsUECQ3fR_vX5w/viewform) to the test in Google forms__ </u>:   
    The data represent the results of passing this test by all my friends and acquaintances of people, who can vouch for the degree of their commitment to gender bias (CGB).
  The purpose of the classification is to determine whether the respondent is free from gender prejudice - "Human" (H), or 
 "Female" (F)/"Male" (M), or a type combining gender stereotypes "male-human" (MH)/ "female-human" (FH).
 
## Methodology
Logistic regression will be used to solve the classification problem, since interpretability is extremely important in this study, and this also takes into account the rank nature of the answers to the question.  
It was decided that a two-stage classification was more appropriate.  
__In the first stage__ we must maximize _Recall_ (TRP), because H recognition is the highest priority and also not forget about _Precission_ (PPV), but if a FH is identified as a H, it is not a big loss. The F-score metric with a weight equal to the ratio of 4:1, that is, 0.8, is best suited for this.  
__In the second stage__, just _accuracy_ will be used as a metric to separate "hf" and "f".  
Also, since the sample is small and the variance associated with VAR is high, it is necessary to use a CV of reducing it.
## Results
Based on the results of training and testing of models, the model proved to be the most effective when dividing data by gender, reaching F1 measures (since no way has yet been developed to use F4) 0.95 for men and 0.98 for women, this is probably due to the larger statistics of this group., compared with 0.83 without gender separation on test data. This model is able to accurately determine the level of gender bias of respondents.  
## Conclusions   
The best features have also been selected:
- CO_3
- TS (MR_8, NUT_9)
- WA_4
- WBW_7  

##__Future plans:__
- Make a multi-class classification based on probabilities. This will correspond to the spirit of research to a more significant extent, because there are no "pure" types, and each person is an amalgam in a certain proportion.
- It is planned to make the second stage of classification of pure types "F" and "M" from those mixed with the accuracy metric
- Create a telegram bot as a simple deployment solution.
- Create a second iteration of the test with the exclusion of unimportant questions and the addition of others to improve subsequent classification and confirm sociological hypotheses.

