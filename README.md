# WQD7005_AA1
# Chong Hun Yee (S2197999)

# Project Overview
The project's goal is to predict customer churn in order to aid in proactive customer retention strategies. Customer information, purchase history, and behaviors are all included in the dataset. This study uses SEMMA methodology which stands for Sample, Explore, Modify, Model, and Assess using SAS e-Miner, Talend Data Integration as well as Talend Data Prep. Talend Data Integration is in charge of Extract, transform, and load (ETL) processes, whereas Talend Data Prep is in charge of data cleanliness to produce good quality dataset. SAS E-Miner is essential for sampling, detailed analysis, data exploration, imputation, feature engineering, data modification and modelling. The ultimate goal is to predict churn prediction effectively model that will allow businesses to identify and retain at-risk customers.

# Objectives
The primary goal of this assignment is to leverage the churn dataset for predicting and understanding customer churn for the past few years. The objectives throughout this assessment is as follows:-
i)	To identify the trend, patterns and the factors contributing to the customers’ churn.
ii)	To study the relationship between the customers’ churn and other variables.

# Tools’ Roles and Justification
## Talend Data Integration
In this project, Talend Data Integration is chosen because it allows task like merging 2 different datasets together easily. In doing this, I do not need to combine the dataset one by one manually with will take a long time. Besides, after merging, the dataset is huge whereby it consists of 250,000 rows and 13 columns. 
![image](https://github.com/chonghunyee/WQD7005_AA1/assets/155872445/f581f076-25b6-422c-b2b3-99993778ad1e)

## Talend Data Preparation
Talend Data Prep tool is selected due to its ability in preparing data, including data cleaning and transformation steps. In this project, this tool is used to handle data inconsistencies as well as to transform data which is to transform the date format to YYYY-MM-DD.
![image](https://github.com/chonghunyee/WQD7005_AA1/assets/155872445/7c41d48d-0d34-4da2-8583-57ec993d0d8f)

## SAS Enterprise-Miner
SAS Enterprise-Miner is used because of its ability to do stratified sampling, data imputation, data modification, data modelling and model assessing. To further elaborate, for sampling phase, stratified random sampling is applied where only 10% of the dataset is used for this project. This can be seen where it helps to reduce the number of rows from 250,000 to 25,000 rows. Besides, it also allows data modification to drop variable such as CustomerID which is not significant in this project and will not affect the customer churn prediction. In addition, data imputation is also done by imputing the missing values of “ProductReturns” columns with “count” or mode. Lastly, this tool assists in building data mining models, including decision trees, HP forest, and Gradient Boosting. It also provides models’ performances evaluation which is under the “Assess” phase in SEMMA methodology.
![image](https://github.com/chonghunyee/WQD7005_AA1/assets/155872445/27d5b976-892d-4f51-8f12-78a9576fa4dc)

# Steps In Using Each Tool
## Talend Data Integration
1)	Open Talend Data Integration Studio.
2)	Launch the Talend Data Integration tool and create a new project.
3)	Right-click in the Repository panel on the left under Job Designs.
4)	Choose Create job. Provide a name for the job which is “combine two files” and a description. Click Finish.
5)	Add 2 tFileInputDelimited Components in order to read 2 delimited CSV files which are the general file and sales file.
6)	From the Palette panel on the right, type "tFileInputDelimited" into the search bar.
7)	For input Data, drag and drop tFileInputDelimited components from the palette onto the workspace for both CSV files. Configure each component to point to the respective CSV files. Ensure you define the schema correctly for each CSV.
8)	tMap Configuration. Drag and drop a tMap component onto the workspace. Link both tFileInputDelimited components to the tMap component. Double click the tMap component to open its editor.
9)	For data joining, On the left side of the tMap editor, you will see the two input datasets. Drag the CustomerID column from task1_customers to the other dataset where it will combine using the CustomerID key. On the right side of the tMap editor, define your output structure. 
10)	Configure tFileOutputDelimited. Double-click on the component. Set the file path where you want to save the filtered data. Ensure the output schema matches the input schema. Define the CSV format, e.g., delimiter as ",".
11)	Run the job.
12)	Save the job.
13)	Click on the "Run" tab at the bottom. Click on the "Run" button. The job will process and merge 2 files into a CSV file.

## Talend Data Preparation
1)	Open Talend Data Prep tool and import the merged dataset into this tool.
2)	For the Gender column, replace from Female to “F” and Male to “M”.
3)	For Location column, replace USA to US
4)	For FavouriteCategory column, change “cloth” to “Clothing”.
5)	For LastPurchaseDate column, transform date column to “yyyy-MM-dd”.
6)	Export the dataset into CSV file for further analysis in SAS Enterprise Miner, as well as export to local Tableau file for reporting purposes.

## SAS Enterprise-Miner
1)	Open and launch SAS Enterprise-Miner which is the local SAS version, and SAS On Demand for academics which the cloud version.
2)	Create a new diagram named “Final Exam”, upload the dataset into the cloud version as well as create a new library.
3)	In the local SAS, create a new data source by editing the data type of each variable clearly and state the target variables.
4)	By using the “Sample” node, do stratified random sampling using 10% of the original dataset. Right click and run.
5)	Drag the “Drop” node, whereby “CustomerID” column is dropped. Right click and run.
6)	Then, drag the “Impute” node, to handle missing data for “ProductReturns” column by using “count”. Right click and run.
7)	Then, split the dataset into 70% of train, 30% of validation and 0% for test on the left panel. Right click and run.
8)	For modelling, Decision Tree, HP Forest and Gradient Boosting nodes are dragged from the model section. Right click and run.
9)	Under the Assess section, drop the “Model Comparison” and connect all the models to it. Right click and run.

# Overall Result and Analysis
Overall, from all the different types of graphs plotted in this project, the visualizations provide useful information about various aspects of the dataset. The line graph reveals significant customer preferences, with "Home" being the least preferred category and "Books" being the most preferred, emphasizing distinct spending patterns. Examining the distribution of "LastPurchaseDate" reveals an out-of-the-ordinary pattern, implying potential irregularities in purchasing behaviour over time. The pie chart shows a significant imbalance in the "Churn" variable, with approximately 20.013% indicating no churn "0" and only 4.987% indicating churn "1". This implies that instances with no churn predominate. This trend is reinforced by the histogram depicting age distribution, which shows a higher number of instances with "Churn" value "0" compared to "1." Finally, the non-normal distribution of "TotalSpent" versus "Age" highlights potential complexities in the relationship between age and total spending. Overall, these visualizations help to provide a more complete understanding of customer behavior, churn patterns, and potential areas for additional analysis or model refinement.

# Future Strategies/ Improvement
For future business strategies, it is critical to ensure that the dataset used for analysis is representative of real-world scenarios. This improves the findings relevance and applicability to practical situations in real business world. A closer alignment with real-world data allows for a more accurate understanding of customer behaviour. As a result, more effective solutions to real-world problems. Furthermore, given more time and resources, a strategic next step could involve SAS feature selection. The goal of this process is to identify and prioritize the most important variables in predicting customer churn. We can improve the model's accuracy and interpretability by utilizing advanced feature selection techniques within SAS, resulting in more robust and reliable predictions. This step is consistent with our ongoing commitment to improving our model's predictive capabilities and practical utility in real-world applications. In doing all these business strategies, the future researchers or businessman can manage and analyze their data well in this business field.

# Reflections or Learning Outcomes
Throughout this project, the most important outcome to me is to implement the 3 tools which I have learnt in class into this alternative assessment or project. These 3 tools which I use in this project are Talend Data Integration, Talend Data Prep, and SAS Enterprise Miner. I gained valuable insights and learning outcomes throughout the course of this project. The SEMMA (Sample, Explore, Modify, Model, Assess) methodology was used to provide a structured approach to predicting customer churn. 

On the other hand, I successfully used data mining models in SAS Enterprise Miner by utilizing decision trees, HP Forest as bagging model, and Gradient boosting as boosting model. With this tool, I am able to compare all these 3 models’ performances easily without doing codes. 

Besides, Talend Data Integration is very helpful in merging 2 separate datasets together with ease. By using this tool, the dataset becomes complete and ready for analysis. 

Moreover, Talend Data Prep was helpful in data cleaning and transformation. To further elaborate on this, it helps to tackle issues such as data inconsistency and date format discrepancies in an easy-to-understand manner. Additionally, it has a very friendly interface where I can use it and clean my data easily. 

In my opinion, this project allows me to show my project management as well as problem solving skills efficiently and effectively. Furthermore, the project demonstrated the application of acquired knowledge to a real-world Kaggle dataset, emphasizing the ability to apply theoretical concepts into practical solutions for predicting customer churn.

In a nutshell, reporting skill is also crucial to present the project results by using a word document as well as GitHub. GitHub is a well-know website used by all researchers, data scientists and data analysts all around the globe. By publishing my work into GitHub, it allows other people to follow my step-by-step implementation using SEMMA methodology with 3 tools. They are able to follow as well as correct my mistakes. This project also provides valuable insights with visualization for readers to understand well. Overall, the project provided a comprehensive understanding of the end-to-end data analysis process as well as its practical application in solving real-world business problems.

