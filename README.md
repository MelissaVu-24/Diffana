# Diffana (in progress)
This project tool is aimed to conduct a differential expression analysis on an RSEM dataset that is in the format *.genes.results of genes for two different conditions. It is supposed to be similar to the Deseq2 tool, where it will compare the datasets of the different conditions to find which genes are differentially expressed. The tool will output a file in the format of .csv which includes a log2FoldChange and a p-value column. The p-value is predicted using Poisson distribution. If the count for a gene is 0, the p-value will be NA

## Installation Instructions:

You may install the tool using this way:
```
git clone https://github.com/MelissaVu-24/Diffana
cd Diffana
python setup.py install
```  
You can also manually download the package
If you do not have root access, instead use:
  `python setup.py install --user`

The tool is installed in the folder shown during the installation

To test that the tool is installed use:

  `diffana --help`
  
## Basic Usage Instructions:
The basic usage is:

  `diffana [--RSEMcon control.genes.results] [--RSEMexp experiment.genes.results] [other options]`
  
  
To run diffana on test examples from files in this repo:

  `diffana --RSEMcon contest1.genes.results --RSEMcon contest2.genes.results --RSEMexp exptest1.genes.results --RSEMexp exptest2.genes.results` 
  
It should produce output like this:
```
"","log2FoldChange","pvalue"
"ENSMUSG00000000001",-0.0656500120.937615884
"ENSMUSG00000000003",0,NA
```
  
## diffana options:
    
    *`--RSEMcon`: The Input RSEM file for the control. This option can be called multiple times. At least one file must be entered. Needs to be called at least twice
    
    *`--RSEMexp`: The Input RSEM file for the experimental. This option can be called multiple times. At least one file must be entered. Needs to be called at least twice

    *`-o File`, `-out File`: Write the output to a file in the csv form. Default will print to stdout.
    
    *`-vp File`: Create a volcano plot and save it to the file given. Default will be None.
    
# Contributors

This repository was generated by Owin Gong and Melissa Vu, with inspiration from the [Deseq2]([https://github.com/gymreklab/trtools].


