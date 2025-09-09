# ShinyCluster 
ShinyCLUSTER is an R Shiny app that can cluster and generate a dendrogram of molecules from a dataset that contains Mass Spec features. The molecules do not need to have known structure and thus this app can be used to infer the structural properties of unknown molecules from the molecules with known identities in the dataset. If abundance data (ie fold change values) for sample comparisons exist for the molecules in the dataset, then these abundance values can be displayed alongside the dendrograms as heatmap rings. This allows for a quick visual identification of groups of molecules with similar structures that have similar fold change values.

![alt_text](https://github.com/allison-d/Cluster/blob/main/docs/assets/dendrogram.png)

## Objective
The goal of the ShinyCluster app is to provide a tool which aids in the identification of unknown compounds in Mass Spec datasets. By using Mass Spec features to cluster molecules with unknown structures along with those with known structures, one can obtain information about potential key features of unknown compounds based on other molecules that belong to the same clade. This tool also allows for the identification of any molecules which might be clear outliers relative to the other molecules in the dataset. Prior to the clustering step, the app presents users with the option to generate scatter plots of the Mass Spec features as well as Kendrick mass defect (KMD) values. These types of plots can be used in identifying outliers, as well as used to visualize homologous series through the KMD values and correlations between features. 


is to house code that is currently being used by members of the bioinformatics team. In addition, it will give team members the opportunity to review and comment on any newly written code.  Bioinformatics analyses frequently need to be updated based on upgrades in sequencing technologies and software. Thus, it will be helpful to have the most recent code for varying project types available in one central location. 

## Structure

The site will be structured based on the type of project. This will help team members easily identify where a specific script might be located and will also enable new folders to be added without any disruption to existing folders. A list of folders that might be included in this repository: 

- RNA-seq (bulk) differential expression
- scRNA-seq
- Transcript Assembly
- Genome Assembly (short-reads)
- Genome Assembly (long-reads)
- Metagenomics
  
## Repository Organization

```
.
├── AUTHORS.md
├── LICENSE
├── README.md
├── mkdocs.yml                      <- Main file for website building
├── requirements.txt                <- Requirements file for website installation
├── code
|  ├── RNA-seq
|  |  ├── bulk    
│  |  |  ├── script.sh               <- analysis script
│  |  |  └── README.md               <- comments about code and the location of test data that can be used to test the script
│  |  └── scRNA-seq
|  |    ├── script.sh               <- analysis script
│  |    └── README.md               <- comments about code and the location of test data that can be used to test the script           
│  ├── Assembly                        <- the assembly folders will contain similar script.sh and README.md files as for RNA-seq               
│  |  ├── Transcript
|  |  ├── Genome (short reads)
|  |  └── Genome (long reads)
|  └── Metagenomics                    <- the metagenomics folder will contain similar script.sh and README.md files as for RNA-seq
└── docs                           
  ├── assets                      <- Folder for website images
  ├── stylesheets                 <- Folder containing style-related code for the website
  ├── index.md                    <- Main website home page
  ├── Data_Management_Plan.md     <- Data Management Plan
  └── Governance_Operations.md    <- Governance & Operations file
```
