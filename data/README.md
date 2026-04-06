# Data Folder

Place the BIGTARGET dataset here after downloading from Kaggle.

This folder is intentionally left empty due to file size constraints.

## Loading data: 

Before running any code, make sure you load the dataset properly by pointing the pathway
to your dataset file correctly, and ensuring the name of the .csv is consistent throughout your .qmd file. 

Replace: 

target <- read.csv("/Users/nuria/Desktop/DS Capstone/BIGTARGET.csv")
head(target, 1)

With (e.g.): 
read.csv("data/BIGTARGET.csv")
