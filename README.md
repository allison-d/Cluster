# ShinyCluster 
ShinyCluster is an R Shiny app that can use Mass Spec features to cluster molecules and generate a dendrogram. The app is a visualization tool that can aid in the identification of unknown molecules through clustering with molecules in the dataset that have known structures. If abundance fold change values for sample comparisons exist for the dataset, then these abundance values can be displayed alongside the dendrograms as heatmap rings. This allows one to quickly ascertain whether molecules with similar structures also have similar fold change values. The ShinyCluster dendrogram visualizations are based on those generated with the SCOPE toolbox (Structural-based connectivity and omic phenotype evaluations) [1]. SCOPE uses simplified molecular-input line-entry system (SMILES) annotations to cluster lipid molecules and the source code for SCOPE can be found here: https://github.com/BakerLabMS/SCOPE

![alt_text](https://github.com/allison-d/Cluster/blob/main/docs/For_github.png)

## Objective
The goal of ShinyCluster is to provide a tool which can aid in the identification of unknown compounds in large Mass Spec datasets. By using Mass Spec features to cluster datasets that contain molecules with unknown structures as well as molecules that have known structures, one can obtain structural information about features of unknown compounds based on other molecules found in the same or nearby clades. This tool also allows for the identification of molecules which might be outliers relative to the other molecules in the dataset. Prior to the clustering step, ShinyCluster presents users with the option of generating scatter plots of the Mass Spec features and Kendrick mass defect (KMD) values with base groups CH2 and CF2. These scatter plots can be used to examine specific feature values for potential outliers, as well as identifiy the existence of homologous series through the KMD values and visualize correlations between sets of features. 

## Directory Organization
There are 3 R files that are used to run ShinyCluster: app.R, server.R, and ui.R. These files are found in the 'code' directory and the files in this directory are shown below. In addition to these R files, the CSV files for two test datasets are located in the 'data' directory. 

```
.
├── app.R
├── server.R
├── ui.R
└── data
  ├── Lipid_Features.csv
  ├── Lipid_Colors.csv    
  ├── Lipid_log2_fold_change.csv 
  ├── PFAS_Features.csv                                     
  └── PFAS_Colors.csv                 
```

## Running ShinyCluster
ShinyCluster can be run in an R environment. The following R libraries are needed to run ShinyCluster:

- shiny
- dplyr
- plotly
- ggtree
- bslib

Two possible methods for running ShinyCluster include the R console and RStudio. Both methods will open ShinyCluster in a new RStudio window. The app can either be run through this window, or in a Browser with the 'Open in Browser' link. ShinyCluster has six tabs, where the first tab 'Overview' describes
the expected file formats for the CSV files that are uploaded to the app.

1. R console: after installing the R libraries, one can run the following lines after adding their path to the 'code' directory in runApp().

```
library(shiny)
shiny::runApp("path to the code directory")
```

2. RStudio: the app can be run by first opening the app.R file in RStudio and then using 'Run App' in the upper right-hand corner. 
One note is that app.R may need to be modified depending on the current working directory of RStudio. If app.R is opened in starting from the 'code' directory, 
then the current working directory in RStudio should be the 'code' directory and 'Run App' should work without any modifications to runApp() located in the second line of app.R. 
If alternatively RStudio is already open and app.R is opened through File --> Open File, then the current working directory may not be that of the 'code' directory. The working directory can be obtained with getwd(). 
If the 'code' directory is not the current working directory, then the path to the 'code' directory needs to be added to runApp() ie runApp("path to the code directory"). 

If one gets the following Error with 'Run App':

Error in `shinyAppDir()`:
! App dir must contain either app.R or server.R
Run `rlang::last_trace()` to see where the error occurred

then check the current working directory to see if it is equal to that of the 'code' directory. If not, then modify runApp() as:
runApp("path to the code directory")

## Test Datasets
There are two test datasets that are available for ShinyCluster. The first dataset contains Mass Spec features for lipid molecules [2] and the second dataset contains PFAS molecules [3]. These CSV files can be used as examples for running ShinyCluster. Both datasets include a CSV file that includes that 
Mass Spec features and a CSV file that specifies the group colors. In addition, the lipid dataset includes a CSV file that includes sample comparison abundance data. Once the app is open, the files for these two test datasets can be uploaded in the following tabs: 

### Lipid set
- Lipid_Features.csv : 'Step 1 - Upload Feature Data'
- Lipid_Colors.csv : 'Step 2 - Upload Group Colors'
- Lipid_log2_fold_change.csv' : 'Step 4 - Upload Abundance Data'

### PFAS set
- PFAS_Features.csv : 'Step 1 - Upload Feature Data'
- PFAS_Colors.csv : 'Step 2 - Upload Group Colors'

## References
[1] Odenkirk, M.T., Zin, P., Ash, J.R., Reif, D.M., Fourches, D., Baker, E.S., 2020. Structural-based connectivity and omic phenotype evaluations (SCOPE): A cheminformatics toolbox for investigating lipidomic changes in complex systems. Analyst 145, 7197–7209.
https://pubs.rsc.org/en/content/articlelanding/2020/an/d0an01638a

[2] Kirkwood-Donelson, K.I., Chappel, J., Tobin, E., Dodds, J.N., Reif, D.M., DeWitt, J.C., Baker, E.S, 2024. Investigating mouse hepatic lipidome dysregulation following exposure to emerging per- and polyfluoroalkyl substances (PFAS). Chemosphere 354, 141654.
https://www.sciencedirect.com/science/article/pii/S0045653524005472

[3] Kirkwood-Donelson, K.I., Dodds, J.N., Schnetzer, A., Hall, N., Baker, E.S., 2023. Uncovering per- and polyfluoroalkyl substances (PFAS) with nontargeted ion mobility spectrometry-mass spectrometry analyses. Sci. Adv. 9, eadj7048.
https://www.science.org/doi/10.1126/sciadv.adj7048 
