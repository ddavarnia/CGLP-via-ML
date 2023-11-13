# CGLP-via-ML
The codes for the machine learning algorithms to solve cut-generating linear programs

This is the implementation used to produce the computational results in the following paper:

* A. Rajabalizadeh and D. Davarnia: Solving a Class of Cut-Generating Linear Programs via Machine Learning, INFORMS Journal on Computing, To appear.

In this paper, we propose a novel framework based on machine learning to approximate the optimal value of a CGLP class that determines whether a cutting plane can be generated at a node of the branch-and-bound tree.

The main requirements are CPLEX solver Version 12.8.0. Python 2.7 with numpy, math, cplex, and sklearn are required to process data and solve the instances.

Pleas note that ongoing maintenance and support for this repository are not provided. Its primary goal is to assist in reproducing the results presented in the above paper. Nevertheless, you are welcome to adapt and customize it to your own needs.

In addition to the code and scripts necessary for replicating the main experiments of the paper, we have included examples from the runs conducted for the paper. Please note that complete output files have been omitted due to their size.

All the codes and data are divided into two sections. Section one has all the code and data related to Convex Hull Membership problem (CHM) and they are saved in CHM folder. There is another section that is related to all the experiments on synthetic instances for the branch-and-bound approach and are saved in B&B folder.

Instructions for CHM folder:

In order to reproduce the results of CHM section, you need to perform the following steps:

1- Generate Linear program instances: To create your general Linear Programs (LPs), use "1-GeneratingLP.ipynb" file. Change the parameters to specify the folder and example name for saving your example data, along with the desired number of constraints and variables. You can skip this step if you prefer to use the pre-existing problems stored in the data folder.

2- Create additional constraints: In certain experiments mentioned in the paper, we examine the impact of redundant constraints on the data. Once you configure the parameters in "2_Adding_redundant_constraints.ipynb" and run it, the new Linear Programs will be generated and stored in the specified folder. Feel free to omit this step if you're not interested in testing redundancy.

3- Generate train set: Generate a training set by using the "3_Generating_train_data.ipynb" notebook for a specific Linear Program. The resulting training set will be saved in the same folder as the corresponding LP.

4- Generate test set: Generate a test set by using the "4_Generating_test_data.ipynb" notebook for a specific Linear Program. The resulting test set will be saved in the same folder as the corresponding LP.

5- Run classification algorithm. After saving train and test set, use "5_Machine_learning.ipynb" to classify your data. Feel free to change the parameters of each model. The result of each classification model with be saved in a seperate file.


Instructions for B&B folder:

Within this folder, there is no specific order for running the notebooks. Depending on the experiment, open the relevant notebook. After configuring the parameters, execute it, and the results will be saved in the same folder as the corresponding Linear Program.

