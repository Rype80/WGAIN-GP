# WGAIN-GP
A complete method to predict order satisfaction using the GAIN framework as imputation method. The GAIN methods also can be used seperately to impute other datasets. 
The zip-file contains all the necessary functions. The information about all the files is given below: 

# In the zip-file many files are created. The information of the files is as follows:
0.  datapreprocessing: R-file which concatenates the datasets of multiple years and transforms some variables.
1.  dataprocessing: file that clears data and prepares it for the file CrossRoads
2.  CrossRoads: File which splits the data for the model tree and GAIN imputation. 
               Furthermore, we obtain the empirical probabilities for coinflipping
               in this file
3.  CompleteGAIN, CompleteWGAIN and CompleteWGAIN-GP: The three GAIN models
4.  GAINHub: File which is used to determine which generator is selected based on 
            different configurations. For this, we apply K-CV (you can select your own K)
5.  MainModelTree: File in which the results of the model tree are computed
6   EmbedPret: File which contains general embedding functions. Used for the GAIN methods
7.  DeStilleFotograaf: File in which plotting functions are stored
8.  SupportGAIN: File in which supportive GAIN functions are stored. These are used 
                in the GAIN methods. 
9   veinGAIN: File in which functions are stored for GAINHub
10. data_loader: File which contains functions which load the data.

All these files can be run independently, in case data is already provided. 
However, in case not, the main order of the files is as follows:
datapreprocessing  --> dataprocessing--> CrossRoads --> GainHub --> MainModelTree
All files not mentioned in this sequence, support at least one of these files. 

Since it takes some time to train the GAIN methods, we also have provided already trained generators in the map
Generators. In this map, we have stored them in the map BatchNorm (main text model) and Advanced (Appendix model)

In order for the code to work, it is recommended to use python 3.8.5.
Furthermore, the following libraries are required to be installed:
1. numpy
2. matplotlib
3. tqdm
4. tensorflow (2.3.0)
5. scikitlearn
6. pandas

In order to install the libraries, we used conda version 4.9.2

In additiom some paths need to be set, and some maps have to be created in order to store plots
and generators. The following paths have to be created in the following files
1.  datapreprocessing: working directory: path from which we select the bol.com data of 2019 and 2020 
		      out_path:path to save data. Path needs to end with GAIN_CODE/Data/ 
2.  dataprocessing: path to load raw data (same path as processed data is stored)
3.  CrossRoads: out_path: path to load and store data; empirical_path: path to store empirical distributions
4.  GAINHub: out_path: path to store plots; CV_path: path to store configuration settings of hyperparameter;
             generator_path: path to save generators (ideally same path as already provided generators are stored)
5.  MainModelTree: out_path: path to load tree data (same path as the path out_path in CrossRoads); 
                   generator_path: path to load generators; empirical_path: path to load empirical distributions

The following maps are required:
1. Data: Map in which all the data is stored. This contains data coming from R, and the datasets required for GAINHub and MainModelTree
2. Empirical: Map in which the empirical distributions are stored
3. Generators: Map in which the generators are stored. Additionally, we already have stored some trained generators
4. CV: Map in which configurations of GainHub are stored
5. Plots: Map in which plots the GAIN methods are stored and used for a bigger plot. 






