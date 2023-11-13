# CGLP-via-ML

This repository contains the source code and data to related to the computational results in the following paper:

* A. Rajabalizadeh and D. Davarnia: **Solving a Class of Cut-Generating Linear Programs via Machine Learning**, *INFORMS Journal on Computing* (2023), To appear.

In this paper, we propose a novel framework based on machine learning to approximate the optimal value of a CGLP class that determines whether a cutting plane can be generated at a node of the branch-and-bound tree.

The main requirements are CPLEX solver Version 12.8.0. Python 2.7 with numpy, math, cplex, and sklearn are required to process data and solve the instances.

***Pleas note that ongoing maintenance and support for this repository are not provided. Its primary goal is to assist in reproducing the results presented in the above paper. Nevertheless, you are welcome to adapt and customize it to your own needs.***

In addition to the code and scripts necessary for replicating the main experiments of the paper, we have included examples from the runs conducted for the paper. Please note that complete output files and the codes related to complemetary experiments have been omitted due to their large size.

The codes and data are divided into two sections. The first section has all the code and data related to the Convex Hull Membership problem (CHM) and they are reported in CHM folder. The second section contains the code and experiments for synthetic instances for the branch-and-bound approach and are saved in B&B folder. The instance for the benchmark problems can be found in [MIPLib 2](https://miplib2010.zib.de/miplib2/miplib2.html). 


# Instructions for CHM Folder:

In order to reproduce the results of CHM experiments, you would need to perform the following steps:

1. Generate linear program instances: To create your general Linear Programs (LPs), use `1-GeneratingLP.ipynb` file. Change the parameters to specify the folder and example name for saving your example data, along with the desired number of constraints and variables. You can skip this step if you prefer to use the pre-existing problem instances stored in the `data` folder.

2. Generate training set: Generate a training set by using the `2_Generating_train_data.ipynb` notebook for a specific LP. The resulting training set will be saved in the same folder as the corresponding LP.

3. Generate test set: Generate a test set by using the `3_Generating_test_data.ipynb` notebook for a specific LP. The resulting test set will be saved in the same folder as the corresponding LP.

4. Run classification algorithm. After saving training and test set, use `4_Machine_learning.ipynb` to classify your data. Feel free to change the parameters of each model. The result of each classification model with be saved in a seperate file.


# Instructions for B&B Folder:

In the folder `BB`, there is no specific order for running the notebooks. Depending on the experiment, open the relevant notebook. After configuring the parameters, execute it, and the results will be saved in the same folder as the corresponding LP. In addition to the folder `data` that contains the synthetic test instances (in LP format) for the B&B experiments, this folder contains following files:

* `BB_Consistency`: This file includes the code to generate consistency cuts through the branch-and-bound process.
* `ML_Consistency`: This file includes the code to use the ML approach to approximate the outcome of the CGLP through the branch-and-bound process. 



