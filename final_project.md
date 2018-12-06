The Association of Smoking and the Risk of Developing Breast Cancer in the United States, Using NHANES 2011-16 Datasets
================
Sha Tao (st3117), Jingqi Song (js5165), Yixuan Wang (yw3095), Ditian Li (dl3157), Boya Guo (bg2604)
December 6, 2018

### Motivation and Related Works

Breast cancer is the most commonly diagnosed cancer among American women. It is estimated that about 1 in 8 U.S women will develop invasive breast cancer over the course of lifetime. An inverse association between smoking and breast cancer survival rate has been reported by many studies. A history of cigarette smoking can significantly increase the risk of breast cancer. However, there is a limited number of prior literatures investigate the association of smoking and breast cancer at a population level using national survey data. To address this knowledge gap, we conduct this secondary data analysis study on the National Health and Nutrition Examination Survey (NHANES) from year 2011 to 2016 to see if there is a trend of smoking and breast cancer risk across years in the United States.

The key predictor of interest was established using the question on “have you smoked at least 100 cigarettes in your entire life”. The outcome of this study used the question “what kind of cancer was it”. Other covariates such as race, age, alcohol, overweight, income, and age at the first birth were identified based on literature review from Pubmed.

### Initial Questions:

Does the risk of breast cancer increases with heavy smoking in the United States, when we controlling for other covariates?

### Data

**Source** We used the Demographics and Questionnaire data files from the NHANES 2011-2016 datasets (<https://wwwn.cdc.gov/nchs/nhanes/Default.aspx>). NHANES is a nationally representative, multi-stage complex survey designed to assess the health and nutritional status of the non-institutionalized, civilian US population.

**Scraping Method and Cleaning**

To investigate the association between smoking and risk of breast cancer across racial/ethnic groups from 2011 to 2016, we pooled the Demographics (demo), Weight History (whq), Medical Conditions (mcq), Smoking History (smq), Alcohol (alq), and Income (inq) data files for each survey cycle using the urls. Then, we merged and tidied our data. We recoded “refused” (7 or 77 or 777) “don't know” (9, 99, 999, 9999) responses as missing value.

### Weighting in NHANES Dataset

Weights variables were created in NHANES dataset to analyze NHANES dataset to account for the complex survey design. NHANES survey consists initial in-home interview, Mobile Examination Centers (MEC) examinations and follow-up questionnaires. The base weights were adjusted for nonresponse to the in-home interview when creating interview weights, and further adjusted for non-response to the MEC exam when creating exam weights. Therefore, to correctly analyze NHANES dataset, we need to consider the effects of weighting on our sample to make a better estimate for the population before we start our analysis.

Based on the tutorial for National Health and Nutrition Examination Survey, we should select the weight of the smallest analysis subpopulation to produce estimates appropriately adjusted for survey non-response. Each NHANES survey cycle is divided into five sections labeled by collection method: Demographics, Dietary, Examination, Laboratory, and Questionnaire. This study only used variables from Demographics and Questionnaire (Weight History, Medical Conditions data files).

Since the Demographics and Questionnaire data were both collected as part of the household interview, the sample weight used for this study should be WTINT2YR, which is the full sample 2-year interview weight. The next step is to construct weights for combined NHANES survey cycles. For a 6-year data from 2011 to 2016, a weight should be constructed as ⅓ \*WTINT2YR. We renamed variable WTINT2YR as ‘weight’ and divided ‘weight’ by 3 to represent the weight from 2011-2016 only using the household interview data.

### Exploratory analysis:

Visualizations, summaries, and exploratory statistical analyses. Justify the steps you took, and show any major changes to your ideas.

### Discussion and Implication:

-   Planned analyses
    -   Analyze the age onset of breast cancer across the total population, and the distribution of smoking incidences across racial/ethnic groups
    -   Use logistic regression to investigate the association between smoking and breast cancer in each race/ethnic groups
-   Visualizations
    -   Boxplot of breast cancer incidences across racial/ethnic groups
    -   Histogram of breast cancer incidences in each age groups
    -   Scatter plot of breast cancer incidences in each racial/ethnic group across 6 years
    -   Perform logistic regression

### References

1.  Bandera, Elisa V., et al. "Racial and Ethnic Disparities in the Impact of smoking on Breast Cancer Risk and Survival: A Global Perspective–." *Advances in Nutrition 6.6 (2015): 803-819.* <https://academic.oup.com/advances/article/6/6/803/4555151>
2.  Chlebowski, Rowan T., et al. "Ethnicity and breast cancer: factors influencing differences in incidence and outcome." *Journal of the National Cancer Institute 97.6 (2005): 439-448.* <https://academic.oup.com/jnci/article/97/6/439/2544155>
3.  Picon‐Ruiz, Manuel, et al. "smoking and adverse breast cancer risk and outcome: mechanistic insights and strategies for intervention." *CA: a cancer journal for clinicians 67.5 (2017): 378-397.* <https://onlinelibrary.wiley.com/doi/full/10.3322/caac.21405>
4.  Module 3: Weighting. National Center for Health Statistics. Centers for Disease Control and Prevention. Retrieved from <https://wwwn.cdc.gov/nchs/nhanes/tutorials/Module3.aspx>
5.  Kispert, S., & McHowat, J. (2017). Recent insights into cigarette smoking as a lifestyle risk factor for breast cancer. Breast Cancer: Targets and Therapy, 9, 127.
