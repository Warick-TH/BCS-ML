# BCS-ML(under construction)
1. Data S1 (All source data obatined from experiments and used for model.), including:
(1) Sheet-Slow pyrolysis of BC: The fast pyrolsis of 9 BCs, usded for calculation of BCS coeffience. The method were detailed illstrated in Method section in Manuscript. After determining the category of MSW, select the corresponding BCs for calculation. The method is to first determine the step size of the coeffience (0-1), then use the traversal method to make the obtained curve closest to the conversion curve of MSW.
(2) Sheet-1BC, 2BCs, 3BCs, ≥4BCs: used for model training and test.
(3) Sheet-Validation experiments result: Validation experiment result and its prediction result obtained through BCS-DNN.

3. model training.ipynb: Training model using random dataset splitting method. All the date used for trainning is provided in Data S1.xlsx. The division ratio of training and testset is set as 7:3 as illustrated in manusrcipt. The DNN or XGB is constructed under the optimal parameters setting as detailed given in paper. 

4. model_parameters_training.pth: The parameters of DNN aftering training, as described in manuscript, which is chosen as the best performing model for further validation.
 
5. Model_val.ipynb: Prediction using the model after training.

