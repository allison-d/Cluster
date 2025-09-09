# ShinyCLUSTER
ShinyCLUSTER is an R Shiny app that can cluster molecules using Mass Spec features. The molecules will be clustered based on the specified features and need not have a known structure. Abundance data for sample comparisons can be displayed alongside the dendrograms as heatmap rings. This allows for a quick visual identification of groups of molecules with similar structures that have similar changes in fold change.

![alt_text](https://github.com/allison-d/Cluster/blob/main/docs/assets/dendrogram.png)

## Objective
The goal of this site is to house code that is currently being used by members of the bioinformatics team. In addition, it will give team members the opportunity to review and comment on any newly written code.  Bioinformatics analyses frequently need to be updated based on upgrades in sequencing technologies and software. Thus, it will be helpful to have the most recent code for varying project types available in one central location. 

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
