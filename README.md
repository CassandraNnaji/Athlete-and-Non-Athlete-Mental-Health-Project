# Athlete-and-Non-Athlete-Mental-Health-Project

## Overview/Business Understanding 
In this project, we will investigate data related to athletes across various sport levels and their mental health conditions. My curiosity about this topic stems from the recognition that athletes experience significant pressure and physical strain depending on their sport level and the nature of their sport. Through interviews and articles, we often hear about the mental health challenges faced by athletes and the factors contributing to these conditions. The primary objective of this project is to uncover insights that reveal the relationship between athletes' sport levels, the types of sports they engage in, and their mental health conditions. Additionally, we aim to develop a predictive model to assess the likelihood of an athlete experiencing a mental health condition. 
Key Questions to Address: 
1.	Does a particular sport level experience a higher prevalence of mental health conditions compared to others?
-	This question aims to explore whether athletes at different levels (e.g., Elite, Semi-Elite, Non-Elite) have varying rates of mental health issues.

2.	Are there specific sports associated with a higher incidence of mental health conditions among athletes?
-	This question seeks to identify whether certain sports are more strongly correlated with mental health challenges.

3.	What factors contribute to the development of mental health conditions among athletes?
-	This question investigates which factors, such as training intensity, competitive pressure, or sport type, are associated with mental health conditions.

4.	Can we build a model to predict whether an athlete will develop a mental health condition?
-	This question focuses on the creation of a predictive model to forecast the likelihood of an athlete experiencing a mental health condition based on available data.

## Data Understanding
This project utilizes data from Figshare.com, published on April 28, 2021, by Christopher Knowles, Stephen Shannon, Garry Prentice, and Gavin Breslin. The dataset, collected through an online survey, contains 68 columns and 860 rows.
“Data collected on athletic identity, resilience, wellbeing, depression, anxiety and loneliness through an online survey using the Mental Health Continuum Short-Form (Keyes, 2005), Hospital Anxiety and Depression Scale (Zigmond and Snaith, 1983), the Brief Resilience Scale (Smith et al., 2008), the Short Loneliness Scale (Gierveld and Tilburg, 2006) and the Athletic Identity Measurement Scale (Brewer et al., 1993). Ethical approval was granted by the Ulster University Research Ethics Filter Committee. No personal identifying information was collected. Participants were all over the age of 18.”

## Modeling and Evaluation
I decided to work with a XGBoost model. The model overall performed with a f1 score of 92%, a recall score of 100%, a precision score of 85% and an accuracy score of 85%.
The Confusion Matrix summarizes the machine's predictions as follows:
•	True Negatives (Upper Left Quadrant): 0 athletes correctly predicted as not suffering from a mental health condition.
•	False Positives (Upper Right Quadrant): 6 athletes incorrectly predicted as having a mental health condition when they do not.
•	False Negatives (Lower Left Quadrant): 0 athletes incorrectly predicted as not having a mental health condition when they actually do.
•	True Positives (Lower Right Quadrant): 35 athletes correctly predicted as having a mental health condition.

## Conclusion
### Data Insights
### Side Note

For this project, I decided to experiment with two different datasets. The first dataset (df2) involved using mode imputation to fill in missing values, while the second dataset (nona_df2) had all missing values removed. My goal was to determine if there were significant differences in insights derived from the two approaches. I found that the primary difference was the volume of data in each dataset, with no major variations in the insights obtained. Ultimately, I chose to use the nona_df2 dataset to build the machine learning model, as it provided a more accurate representation of the data without extensive manipulation.

## Nona_Df2 Dataset

1.	Across all sports, there are more 'Non-Elite' athletes (club, local competition, recreational) compared to Elite athletes (national, professional) and Semi-Elite athletes (semi-professional, county GAA).

2.	
•	The highest participation is observed in (Ball Sports), followed by (Track & Field), (Dance, Gymnastics, and Strength), and (Rowing & Kayaking). Specifically, there are approximately ~110 athletes in Ball Sports, ~53 athletes in Track & Field, ~9 athletes in Dance, Gymnastics, and Strength, and ~8 athletes in Rowing & Kayaking. Other sports have fewer than 3 participants each.
•	Within Ball Sports, there are about ~70 Non-Elite athletes, ~25 Semi-Elite athletes, and ~15 Elite athletes.
•	For Track & Field, there are approximately ~45 Non-Elite athletes, ~5 Semi-Elite athletes, and ~3 Elite athletes.
•	In Dance, Gymnastics, and Strength, there are around ~7 Non-Elite athletes and ~2 Elite athletes.
•	In Rowing & Kayaking, there are about ~3 Non-Elite athletes, ~2 Semi-Elite athletes, and ~3 Elite athletes.

3.	I analyzed the athletes' involvement in structured/rule-bound competitive sports and their weekly practice hours. The findings are as follows:
•	All athletes participate in structured/rule-bound competitive sports.
•	A significant proportion of the athletes practice between 1-5 hours or 6-10 hours per week.

4.	Based on location and sports level, the analysis revealed the following:
•	All athletes in this dataset are from either Ireland or the UK.
•	In Ireland, there are approximately 37 Non-Elite athletes, 10 Semi-Elite athletes, and 10 Elite athletes.
•	In the UK, there are approximately 100 Non-Elite athletes, 25 Semi-Elite athletes, and 15 Elite athletes.

5.	Based on location (Ireland and the UK) and different mental health conditions, the analysis revealed the following:
•	In Ireland, the majority of athletes, approximately 120, do not have a mental health condition. A smaller number of athletes, around 2 each, suffer from Anxiety, Depression, both Depression and Anxiety, or have an unspecified mental health condition.
•	In the UK, the majority of athletes, approximately 53, do not have a mental health condition. A smaller number of athletes, varying under 8 each, suffer from Anxiety, Depression, both Depression and Anxiety, PTSD, or have an unspecified mental health condition.

6.	Based on location (Ireland and the UK), mental health conditions, and typical age groups affected, the analysis revealed the following:

In Ireland:
•	Anxiety Disorder: Only 1 athlete has this condition, and they are in the 18-20 age group.
•	Depression Disorder: 2 athletes have this condition; one is in the 18-20 age group and the other in the 31-40 age group.
•	Depression & Anxiety Disorder: Only 1 athlete has this condition, and they are in the 31-40 age group.
•	Unknown Mental Health Disorder: Only 1 athlete fits in this category, and they are in the 21-30 age group.

In the UK:
•	Anxiety Disorder: 8 athletes have this condition. 3 in the 21-30 age group, 3 in the 31-40 age group, and 2 in the 41-50 age group.
•	Depression Disorder: 5 athletes have this condition. 1 in the 18-20 age group, 2 in the 21-30 age group, and 2 in the 31-40 age group.
•	Depression & Anxiety Disorder: 3 athletes have this condition. 1 in the 18-20 age group, and 2 in the 41-50 age group.
•	Unknown Mental Health Disorder: 4 athletes fit into this category. 1 in the 18-20 age group, 1 in the 21-30 age group, and 2 in the 41-50 age group.
•	PTSD Disorder: 2 athletes have this condition. 1 in the 31-40 age group and 1 in the 51-60 age group.

Overall Determination:
•	Athletes in the dataset aged 18-50 suffer the most from mental health conditions.
•	There are no athletes aged 51+ in the dataset who suffer from any mental health disorder, except for 1 athlete suffering from PTSD.

7.	Upon creating a correlation chart, I found that the only highly correlated variables (with a correlation coefficient greater than 0.5) in the dataset nona_df3 are:
•	'I have a hard time making it through stressful events' and 'It is hard for me to snap back when something bad happens,' with a correlation of 0.626221.
•	'I get sudden feelings of panic' and 'I get a sort of frightened feeling like 'butterflies' in my stomach,' with a correlation of 0.564985.

## Summary of Model Results

1.	Dataset Imbalance: The dataset exhibited moderate to extreme class imbalance, with 86% of the samples classified as 'No' (not suffering from a mental health condition) and 13.8% classified as 'Yes' (suffering from a mental health condition). For the sake of curiosity, I chose to work with the imbalanced dataset rather than applying upsampling or downsampling techniques.
2.	Model Performance with XGBoost: I employed an XGBoost model, which achieved an impressive F1 score of 92% on the test data. However, this high score was primarily due to the weighted F1 score, which adjusts for class frequencies by assigning different weights based on their prevalence in the dataset.
3.	Confusion Matrix Analysis: To further evaluate the model’s performance, I created a Confusion Matrix. This tool allowed me to more comprehensively assess how well the model was predicting the different classes.
4.	Model Reliability: Despite the high F1 score, the model’s predictions proved unreliable. The imbalance in the dataset led to misleadingly high-performance metrics, indicating that the model was not truly effective for making accurate predictions.

## Recommendations / Next Steps

1.	Address Missing Data: The analysis revealed a significant amount of missing data in many key columns. To improve the quality of future datasets, it is recommended that the athletes be resurveyed to ensure complete and accurate responses to all relevant questions. Alternatively, ensuring that the survey completion rates are high for all important questions could improve data reliability.
2.	Focus on Relevant Locations: Given that the majority of the data pertains to athletes in Ireland and the UK, future surveys should be concentrated on these two countries. This approach will ensure that the data collected is more relevant and representative of the target population for this specific study.
3.	Balance Data Across Sports Levels: The current dataset is heavily skewed towards Non-Elite athletes, with fewer Elite and Semi-Elite athletes represented. To achieve a more balanced dataset, efforts should be made to survey a greater number of athletes in the 'Elite' and 'Semi-Elite' categories. A more balanced dataset will allow for a better analysis of how different sports levels relate to mental health conditions.
4.	Develop and Validate Models: Once accurate and balanced data is obtained, constructing a new XGBoost model should be a priority. This model could be used to assess the predictability of mental health conditions among athletes, exploring various factors such as symptoms, emotional influences, and sports levels. Further validation and refinement of the model can provide deeper insights into the factors contributing to mental health issues.

