# Introduction  
This repository provides source code of MISSION.  

MISSION is a data augmentation approach that aims at handling the data imbalanced problem rooted in the natural of the program test suite. Specifically, MISSION
 generates synthesized failing test cases from reduced feature sapce.  

# Environment  
OS: Linux  
Python package:  
pandas==0.25.1  
chardet==3.0.4  
numpy==1.16.5  
torch==1.9.0  

# Structure  
The structure of the repository is as follows:  

calculate_suspiciousness  
|____CalculateSuspiciousness.py	:calculate suspiciousness of each statement and give the MFR rank or MAR rank according to the real fault line.  
data  
|____d4j :Defects4J dataset	  
|____manybugs :MangBugs dataset	  
|____sir :SIR dataset		  
|____motivation :artificial dataset	  
data_process  
|____data_systhesis :data synthesis approaches  
|&ensp;&ensp;&ensp;|____resampling.py  
|&ensp;&ensp;&ensp;|____borderline_smote.py  
|____dimensional_reduction :feature selection   
|&ensp;&ensp;&ensp;|____Slice.py		  
metrics : SFL and DLFL metrics  
|____calc_corr.py  
|____dl_metrics.py  
|____metrics.py  
pipeline  
|____Pipeline.py : load different type of data, process data and calculate suspiciousness task  
read_data : load data according to args  
|____DataLoader.py  
|____Defects4JDataLoader.py  
|____ManyBugsDataLoader.py  
|____SIRDataLoader.py  
utils   
|____args_util.py  
|____file_util.py  
|____read_util.py  
|____write_util.py  
run.py : program entry  

# Usage
To run the program, commandline parameters are needed.

**required arguments: **  
| name | meaning | value |
|----------|----------|----------|
| -d    | dataset   | "d4j", "manybugs","SIR"   |
| -p    | program   | "Chart", "Closure", "Time", "Lang", ...   |
| -i    | bug_id   | "1", "2", ...   |
| -m    | method   | "ochiai", "barinel", "MLP-FL", ...     |
| -e    | experiment   | "resampling", "undersampling", ...    |

 

