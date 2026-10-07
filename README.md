# Practical No. 1

Aim: To install WEKA, explore its major components (Explorer, Experimenter, Knowledge Flow), load sample datasets, and understand ARFF and CSV file formats.

Objectives:
After completing this experiment, students will be able to:
Install WEKA successfully.
Understand the WEKA graphical user interface.
Explore the components of WEKA.
Load datasets into WEKA.
Differentiate between ARFF and CSV file formats.
View dataset attributes and statistics.

Software Required:
WEKA 3.8.x or latest version
Windows/Linux/macOS
Java Runtime Environment (JRE) (if required)

What is WEKA?
WEKA (Waikato Environment for Knowledge Analysis) is an open-source machine learning and data mining software developed by the University of Waikato, New Zealand. It provides a collection of machine learning algorithms for data preprocessing, classification, clustering, association rule mining, visualization, and feature selection.
WEKA supports graphical user interfaces, command-line interface, and Java API.

Components of WEKA:
When WEKA starts, the following options appear:

1. Explorer: Explorer is the most commonly used interface.
Functions:
Load datasets
Data preprocessing
Classification
Clustering
Association Rule Mining
Attribute Selection
Data Visualization

Explorer contains six tabs:
Preprocess
Classify
Cluster
Associate
Select Attributes
Visualize

3. Experimenter:

Experimenter is used to compare the performance of multiple machine learning algorithms on one or more datasets.
Features:
Batch experiments
Statistical comparison
Performance evaluation
Result analysis

5. Knowledge :

Knowledge Flow provides a graphical drag-and-drop environment.
Features:
Visual workflow design
Data loading
Filtering
Classification
Evaluation
Visualization

4. Simple CLI :
Command-line interface for executing WEKA commands manually.


Procedure :-
Part A: Installation of WEKA
Step 1: Download WEKA from the official website.
Step 2: Run the installer.
Step 3: Follow the installation wizard.
Step 4: Launch WEKA.

The following window appears:
WEKA GUI Chooser


Part B: Loading Dataset

After opening the dataset, observe:
Relation Name
Number of Instances
Number of Attributes
Attribute List
Class Attribute
Missing Values
Statistics
Sample Dataset (Iris)
Relation Name

iris

Instances

150

Attributes

5

Class

Species

Understanding ARFF Format:-
ARFF stands for "Attribute Relation File Format"
It consists of two sections.
1. Header:
Contains
Relation name
Attribute names
Attribute types

Example:
@relation iris

@attribute sepallength numeric
@attribute sepalwidth numeric
@attribute petallength numeric
@attribute petalwidth numeric

@attribute class
{Iris-setosa,Iris-versicolor,Iris-virginica}

Data Section:
@data

5.1,3.5,1.4,0.2,Iris-setosa
4.9,3.0,1.4,0.2,Iris-setosa


Understanding CSV Format:
CSV stands for "Comma Separated Values"

Example:
SepalLength,SepalWidth,PetalLength,PetalWidth,Class

5.1,3.5,1.4,0.2,Iris-setosa

4.9,3.0,1.4,0.2,Iris-setosa


Difference Between ARFF and CSV:
ARFF
CSV
Contains metadata
No metadata
Supports attribute types
Does not specify types
Native WEKA format
Universal format
Includes relation name
No relation name
Better for machine learning
Better for data exchange


Observations
Parameter
Value
Dataset Name
iris.arff
Number of Instances
150
Number of Attributes
5
Class Attribute
Species
Missing Values
0






========================================================================================================================================================================================================================================================================================================================================================================================================================================



# Practical No 2

Data Import and Dataset Understanding
Import datasets (CSV/ARFF) in WEKA, examine attributes, summary statistics, and visualize data using preprocessing tools


Data preprocessing is the first and one of the most important steps in Data Mining. Before applying any machine learning algorithm, datasets should be examined for their structure, attribute types, missing values, and statistical information.

WEKA provides a Preprocess panel where users can:
Import datasets
View attribute information
Check missing values
Display summary statistics
Visualize data distributions
Apply preprocessing filters

Part A: Import ARFF Dataset -------- " iris.arff " data has to download.

Step 1
Open WEKA GUI Chooser.

Step 2
Click Explorer.
 
Step 3
Select the Preprocess tab.


Step 4
Click Open File.

Step 6
Dataset loads successfully.

Observe:
Relation Name
Number of Instances
Number of Attributes
Attribute Names
Class Attribute




Part B: Import CSV Dataset 



Part C: Examine Dataset Attributes
On the left side of the Preprocess window --> click each attribute one by one.
Example:

Attribute 1 --> " SepalLength "

Observe:
Type
Missing values
Distinct values
Minimum value
Maximum value
Mean
Standard Deviation



Part D: --> " Select Class "



Part E: Visualize Dataset

Step 1: --> Visualize All

Step 2
Scatter plots appear.
Each graph represents
Attribute vs Attribute
  

Part F: Examine Histograms 
Click any attribute.

Histogram appears on the right side.
Observe
Frequency Distribution
Minimum
Maximum
Missing values




========================================================================================================================================================================================================================================================================================================================================================================================================================================


# Practical No. 3

Data Preprocessing Techniques
Perform preprocessing tasks such as handling missing values, normalization, discretization, and
filtering attributes using WEKA filters.

Data preprocessing is the process of transforming raw data into a clean and suitable format
before applying machine learning algorithms.

Common preprocessing techniques include:
● Handling Missing Values
● Normalization
● Standardization
● Discretization
● Attribute Selection
● Attribute Filtering
● Removing Duplicate Data

WEKA provides these facilities through the Preprocess tab using Filters.

Step 1: Load Dataset

Dataset saved as " studentperformance.arff " --> Steps : open Notepad -> paste the below code in Notepad -> Save as "studentperformance.arff" -> select file type "All Files" -> then save this into your file.

@relation student_performance
@attribute age numeric
@attribute gender {Male, Female}
@attribute study_time_weekly numeric
@attribute absences numeric
@attribute tutoring {Yes, No}
@attribute parental_support {Low, Medium, High}
@attribute grade_class {Pass, Fail}

@data
16, Female, 12.5, 3, Yes, High, Pass
17, Male, 5.0, 14, No, Low, Fail
15, Male, 8.5, 6, No, Medium, Pass
18, Female, 10.0, 9, Yes, Medium, Pass
16, Male, 3.0, 22, No, Low, Fail
17, Female, 15.0, 2, Yes, High, Pass

Open WEKA → Explorer.
        |
Go to the Preprocess tab.
        |
Click Open file → select your dataset " Studentperformance.arff"
        |
Choose a filter:
● In the Preprocess tab, click Choose under Filter.
● ReplaceMissingValues → Handles missing values automatically.    -> unsupervised -> attribute -> ReplaceMissingValues

● Normalize → Scales numeric attributes to [0,1].

● Standardize → Converts numeric attributes to mean = 0, std. dev. = 1.
○ unsupervised → attribute → Standardize


========================================================================================================================================================================================================================================================================================================================================================================================================================================


# Practical 4
Data Cleaning and Transformation
Apply attribute selection, remove noisy data, transform datasets using filters such as Remove, ReplaceMissingValues, and Normalize.

In this practical use "iris.arff" dataset.

● You can include/exclude attributes:
○ Select an attribute → click Remove (e.g., remove ID or Name if they are not useful). 



Click Choose under Filter -> unsupervised -> attribute -> Click the filter name (Remove) to edit options. 

Enter the attribute index. 

Click Apply. 

Remove Noisy Data
Noisy attributes can be removed manually.

Select (Sepallength) -> click on remove.

The selected attribute is removed.


Attribute Selection:
Attribute Selection helps choose the most relevant features.

Go to Choose -> Filters -> supervised -> attribute -> Click on (AttributeSelection).

Click Apply.

End of the practical.
========================================================================================================================================================================================================================================================================================================================================================================================================================================

# Practical 5
Association Rule Mining using Apriori
Apply the Apriori algorithm to generate association rules. Analyze support, confidence, and lift values. Perform a Market Basket Analysis case study.

"""
Association Rule Mining is a data mining technique used to discover interesting relationships between items in a dataset. It is commonly used in Market Basket Analysis, where retailers identify products that are frequently purchased together.
The Apriori Algorithm generates frequent itemsets based on a minimum support threshold and then creates association rules that satisfy a minimum confidence threshold.

Important Measures

1. Support
Support indicates how frequently an itemset appears in the dataset.

Formula:
Support(A→B)=Transactions containing A and BTotal TransactionsSupport(A \rightarrow B)=\frac{Transactions\ containing\ A\ and\ B}{Total\ Transactions}Support(A→B)=Total TransactionsTransactions containing A and B​

3. Confidence
Confidence measures how often item B appears when item A is purchased.
Formula:
Confidence(A→B)=Support(A∩B)Support(A)Confidence(A \rightarrow B)=\frac{Support(A\cap B)}{Support(A)}Confidence(A→B)=Support(A)Support(A∩B)
​
5. Lift
Lift measures the strength of the association between two items.
Formula:
Lift(A→B)=Confidence(A→B)Support(B)Lift(A \rightarrow B)=\frac{Confidence(A\rightarrow B)}{Support(B)}Lift(A→B)=Support(B)Confidence(A→B)
​
Interpretation:
Lift > 1 → Positive association
Lift = 1 → No association
Lift < 1 → Negative association

Sample Market Basket Dataset
Transaction
Items Purchased
T1
Bread, Milk
T2
Bread, Diaper, Beer, Eggs
T3
Milk, Diaper, Beer, Cola
T4
Bread, Milk, Diaper, Beer
T5
Bread, Milk, Diaper, Cola  """"  Ispe itna dhyan mat do ..... niche se chalu karo practical .


Launch WEKA -> Click Explorer -> Open the Preprocess tab -> Click Open File.
                |
Select the Market Basket dataset (marketbasket.arff or CSV) ->  Link -> https://github.com/ramonsaraiva/market-basket-analysis/blob/master/datasets/supermarket.arff  -> then download this file.

Verify that all attributes are loaded correctly.

Click the Associate tab.
        |
Click the Choose button.
        |
Select: Associations → Apriori
        |
Click Start.

WEKA processes the dataset and displays the generated association rules.



========================================================================================================================================================================================================================================================================================================================================================================================================================================


# Practical No. 6
Aim: To implement the Decision Tree (J48) classification algorithm in WEKA, train and test the model using different datasets, and analyze the classification results.

Step 1: Open WEKA
1. Launch WEKA.
2. Click Explorer.

Step 2: Load Dataset
1. Click Open File.
2. Navigate to: data -> weather.nominal.arff -> Download from browser -> Link -> https://gist.github.com/myui/2c9df50db3de93a71b92


3. Select weather.nominal.arff
Click Open.
The dataset summary will appear on the left side.


Step 3: Check Class Attribute
1. Ensure the (Class) attribute is selected.
2. For Iris dataset, the class attribute is: class
 
3. It contains three classes:
	1. Sunny
	2. Overcast
	3. Rainy

Step 4: Go to (Classify) Tab
Click -> Classify


Step 5: Choose Classifier
Click -> Choose -> Navigate to -> trees -> J48 -> Select J48.


Step 6: Set Testing Option
Choose one of the following:

Option 1 (Recommended)
10-Fold Cross Validation
Leave it as default.

OR

Option 2
Percentage Split


Step 7: Start Training
Click
Start
WEKA builds the Decision Tree.

========================================================================================================================================================================================================================================================================================================================================================================================================================================


# Practical N0. 7
Aim
To implement Naïve Bayes and IBk (k-Nearest Neighbors) classification algorithms in WEKA, evaluate their performance using different datasets, and compare the results using evaluation metrics.

Naive Bayes

Step 1: Open WEKA
Launch WEKA.
Click Explorer.


Step 2: Load Dataset
Click Open File -> Select iris.arff -> Click Open.  ("iris.arff" dataset -> download from browser.)

The dataset summary will appear.

Step 3: Verify Class Attribute
Ensure the class attribute is: Class


Step 4: Open Classify Tab
Click the (Classify) tab.


Step 5: Select Naïve Bayes
Click Choose.
Navigate to: bayes -> NaiveBayes -> Select NaiveBayes.


Step 6: Select Test Option
Choose:
10-Fold Cross Validation
(Default option)

OR

Percentage Split (66%)


Step 7: Train the Model
Click
Start


Step 8: Observe Results

WEKA displays:
Correctly Classified Instances
Incorrectly Classified Instances
Kappa Statistic
Mean Absolute Error
Root Mean Squared Error
Precision
Recall
F-Measure
ROC Area
Confusion Matrix

========================================================================================================================================================================================================================================================================================================================================================================================================================================

# Practical 8
Aim:
Model Evaluation Techniques
Evaluate classification models using accuracy, precision, recall, F-measure, and confusion matrix with cross-validation

Step 1: Open WEKA
Launch WEKA.
Click Explorer.


Step 2: Load Dataset
Click Open File.
Select a dataset (e.g., iris.arff). -> ("iris.arff" dataset -> download from browser.)

The dataset summary appears.
Ensure the Class Attribute is correctly selected (usually the last attribute).


Step 3: Go to the Classify Tab
Click the (Classify tab. -> Click the Choose button.


Step 4: Select a Classification Algorithm
Choose any classifier such as:
Trees → J48
Bayes → NaiveBayes
Lazy → IBk (k-NN)  -> Choose any one of them.

Example:
Choose → Trees → J48


Step 5: Select Evaluation Method
Under Test Options, select:
Cross-validation
Set:
Number of folds = 10
This performs 10-Fold Cross Validation.


Step 6: Start Classification
Click Start.
WEKA trains and tests the model.


Step 7: Observe the Results
The output window displays:
Correctly Classified Instances
Incorrectly Classified Instances
Kappa Statistic
Mean Absolute Error
Root Mean Squared Error
Precision
Recall
F-Measure
Confusion Matrix



========================================================================================================================================================================================================================================================================================================================================================================================================================================


# Practical 9
Aim:
Clustering using K-Means
Perform clustering using the SimpleKMeans algorithm and analyze cluster formation with visualization tools.

Step 1: Open WEKA
Launch WEKA.
Click Explorer.


Step 2: Load the Dataset
Click Open File.
Select the dataset (e.g., iris.arff). -> ("iris.arff" dataset -> download from browser.)

The dataset summary will appear in the Preprocess tab.


Step 3: Remove the Class Attribute (Optional)

Since K-Means is an unsupervised learning algorithm, it does not require a class label.

In the Preprocess tab, select the class attribute (e.g., class in Iris).

Click Remove if you want to perform pure clustering.

(Alternatively, you can leave the class attribute and ignore it during clustering.)


Step 4: Go to the Cluster Tab
Click the (Cluster) tab.
Click the Choose button.



Step 5: Select the SimpleKMeans Algorithm
Navigate to: Choose → weka → clusterers → SimpleKMeans
Click SimpleKMeans.


Step 6: Configure the Algorithm

Click on -> SimpleKMeans -> to modify its parameters -> then change numClusters = 3 -> then click ok.

Set the following:

Parameter                                        value 
Number of Clusters (numClusters)                   3
Distance Function                              EuclideanDistance
Seed                                              10
Preserve Order                                   False

Click OK.


Step 7: Select (Use training set).
Use Training Set (for unlabeled datasets).


Step 8: Run the Algorithm
Click Start.
WEKA performs clustering and displays the results.



Step 9: Observe the Output
The output window displays:
Number of clusters
Cluster centroids
Number of instances in each cluster
Within-cluster sum of squared errors
Cluster assignments
Example:
Number of clusters: 3

Cluster 0 : 50 instances

Cluster 1 : 62 instances

Cluster 2 : 38 instances


Step 10: View Cluster Centroids
WEKA displays the centroid values for each cluster.


Step 11: Visualize the Clusters
After clustering, right-click the result in the Result List.
Select Visualize Cluster Assignments.
A scatter plot window opens.
Choose attributes for the X-axis and Y-axis (e.g., Petal Length and Petal Width).
Each cluster is displayed in a different color.
Observe how similar data points are grouped into clusters.



Step 12: Analyze the Results
Check the following:
Number of clusters formed.
Number of instances in each cluster.
Cluster centroids.
Distribution of data points.
Separation between clusters.
Whether similar instances are grouped together.







========================================================================================================================================================================================================================================================================================================================================================================================================================================




# Practical 10
Aim:
Density-Based Clustering (DBSCAN) and Use Case
Implement density-based clustering in WEKA and analyze customer segmentation datasets.

Step 1: Open WEKA
Launch WEKA.
Click Explorer.


Step 2: Load the Dataset

Open Notepad -> 

% Customer Data Example for Weka
@RELATION customer_data

@ATTRIBUTE age NUMERIC
@ATTRIBUTE income NUMERIC
@ATTRIBUTE gender {male, female}
@ATTRIBUTE purchased {yes, no}

@DATA
35, 50000, male, yes
22, 24000, female, no
45, 82000, female, yes
31, 41000, male, no
29, 36000, female, yes

Save the above data as (customer.arff) -> select all file type. -> Then save.

Click Open File.
Select the customer dataset.
The dataset summary will appear in the Preprocess tab.



Step 3: Preprocess the Dataset (Optional)
Check for missing values.
Normalize the numeric attributes (recommended for DBSCAN).
Remove unnecessary attributes such as Customer ID if required.



Step 4: Open the Cluster Tab
Click the Cluster tab.
Click Choose.



Step 5: Select the DBSCAN Algorithm
Navigate to:
Choose → weka → clusterers → MakeDensityBasedCluster
Select MakeDensityBasedCluster.



Step 6: Configure DBSCAN Parameters
Click (MakeDensityBasedCluster) to edit the parameters.

Do not change any parameter here: ----------------
Set the following values:

Parameter                              Example Value
Epsilon (epsilon)                          0.9
Minimum Points (minPoints)                  6
Database Type                          SequentialDatabase

Click OK.

Parameter Description
Epsilon (ε): Maximum distance between neighboring points.
MinPoints: Minimum number of neighboring points required to form a dense cluster.
-----------------------------------------------------------------------

Step 7: Select Cluster Mode
Choose one of the following: -> Use Training Set

Step 8: Run MakeDensityBasedCluster:
Click Start.
WEKA executes the MakeDensityBasedCluster algorithm.



Step 9: Observe the Output
The output window displays:
Number of clusters formed
Number of noise (outlier) instances
Cluster assignments
Cluster statistics
Example:
Number of clusters : 4

Noise Objects : 8

Cluster 0 : 45

Cluster 1 : 32

Cluster 2 : 51
Cluster 3 : 24




Step 10: Visualize Cluster Assignments :

---------------------------------------------
Right-click the result in the Result List.
-------------------------------------------

Select Visualize Cluster Assignments.
A scatter plot opens.
Select suitable attributes for the X-axis and Y-axis.
Observe:
        Different clusters shown in different colors.
        Noise or outlier points displayed separately.



Step 11: Analyze the Results
Observe the following:
          Number of clusters created.
          Number of noise (outlier) points detected.
          Distribution of customers across clusters.
          Separation between dense regions.
          Whether customers with similar characteristics are grouped together.
