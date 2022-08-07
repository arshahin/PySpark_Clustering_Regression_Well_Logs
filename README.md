# PySpark_Clustering_Regression_Well_Logs
A PySpark package for clustering and regression of well logs 
In this package, I use PySpark to do data cleaning, clustering, and then regression on more than 20 wells. I use MLLib.

Steps:

1) Load CSV file
2) Remove outliers and nulls (See instruction below).
3) Rescaling data to [0 1]
4) Exploratory data analysis (EDA). 
5) I do different types of clustering (KNN, Kmean, Spectral, GMM, DBSCAN). Will try 4 and 5 clutters and see which one is better justified. The first column named "Depth" is not included for clustering. I will cluster based on these columns (DT, RHOB, SGR, NPHI, PEF).

6) Visualize the outcome of different clustering techniques and show some score metrics. 

7) Label the original data with clusters labels (1, 2, 3, 4, 5)  by adding an extra column to the data frame.

8) Regression using different methods. Here, I do cluster-based regression meaning regression will be applied on each cluster separately. I test different methods on one cluster and decide which one is the best and then apply the best method for the rest of clusters. I also visualize the residuals and compare the regression predictions with actual measurements. The input variables for regression are DT, RHOB, SGR, NPHI and the output is PEF. Note that we have PEF column, but we want to predict it and then compare it with prediction.
	Linear regression
	Polynomial regression
	Lasso regression
	Kth Nearest Regression (KNR)
	Decision Tree Regression (DTR)
	Gradient Boosting Regression (GBR)
	Random Forest Regression (RFR)
	Adaptive Boosting Regression (ABR)
	Generalized Regression Neural Networks (GRNN)

Instruction to remove the entire rows when they have outlier and/or null values. Note that if any of these conditions are satisfied, the entire row will be deleted.

DT smaller than 0 || DT greater than 100
NPHI smaller than -0.1 || NPHI greater than 0.45
RHOB smaller than 2.0 || RHOB greater than 3.0
PEF smaller than 0.0 || PEF greater than 7.0
RT smaller than 0.0 || RT greater than 2000
GR smaller than 0 || GR greater than150
