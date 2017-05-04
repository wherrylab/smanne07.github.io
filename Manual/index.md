---
layout: post
title: WherryLab tools
subtitle: How to use them

---
[How to use Arraydatabrowser](https://wherrylab.github.io/2017-02-28-ArrayDataBroswer/)
# Limma Based analysis of Microarray/RNA-seq analysis

This tool determines the important features significantly changed between groups by assessing differential expression using linear models implemented in the R package limma.

Input Parameters:

1) .gct file

A tab delimited text file with a .gct extension containing expression data with columns as samples and rows as features(genes/probes e.t.c).

a valid .gct file should have a unique feature name for each row

#1.2

nF nS
Feature Sample1 Sample2 ...

Feature1 val11 val12 ...

Feature2 val21 val22 ...

nF -number of Features/Genes/Probes

nS -number of Samples

2)Experiment design file

a tab delimited text file containing brief information about the experiment samples and their groups

a valid design file should contain rows corresponding to all the samples listed in the .gct file.

Sample Condition/group

Sample1 Group1

Sample2 Group2

. .

. .

. .
The number of the rows in the experiment design file should be equivalent to nS of the .gct file.

3) p value cutoff

a parameter the user chooses to indicate the level of significance to use to determine if a feature/gene is significantly different between groups of comparison

4) fold change cutoff

a parameter the user chooses to set the threshold for fold change (Either direction) to use to determine if a feature/gene is differentially expressed between groups of comparison.

5) two groups to compare

a parameter which is dynamically created based on a valid experiment design the user uploads for the .gct file. Current function is to choose a pair of groups to compare against each other.

6) gene name to check expression

a user choosen gene to check its mean log expression across groups.The user input gene name should match the format(Case sensitive) of the gene names listed in the user supplied gct file Feature field.

7)Run

The run button starts the analysis of the pairwise comparison based on valid user inputs choosen and prints out the output results to the bottom panel.

User can change any parameters and run again to change the bottom panel results.(You can save the results before u change the parameters)

The user can check the expression of a single gene across groups anytime and independently of running the pairwise comparison of groups selected.

Output Results

1)Gene expression

This ouput panel visualizes the mean gene level expression data across all groups and dynamically responds to user input for a valid gene name

This panel works independently of the user choosen parameters for differential expression.

2)DE Genes

This panel plots the log fold change on x-axis and -log p value on y-axis for the genes which are differentially expressed for choosen groups of comparison and based on thresholds for significance and fold change.

This plot is a interactive plot(Zoom/hover) and can be edited/saved on the cloud as it is based on plotly(https://plot.ly/)

3)Genes list & Statistics

This panel is a tabular format of results with list of genes,log fold change,average expression,p value,adjusted p value for the differentialexpression analysis based on user choosen options.

This list can be explored like an excel sheet with options to show fixed number of entries on a page,scroll through pages,sort by a column and multiple search boxes(search works with exact case and spelling only!).

This complete list with statistics can be downloaded with the download button on bottom of results page.

4)GO summary

This panel plots the -log p value on x-axis for enrichment of a Gene ontology term and the frequency(measure of gene matches for a GO term) for the genes which are differentially expressed for choosen groups of comparison and based on thresholds for significance and fold change.

This plot too is a interactive plot(Zoom/hover) and can be edited/saved on the cloud as it is based on plotly(https://plot.ly/)

5)GO list & Statistics

This panel is similar in format to the Genes list & Statistics panel.

This panel is a tabular list of Gene ontology enrichment results with GO_ID,Size(Number of genes in a GO term),Gene_matches(genes overlap between term & differntial genes),P value,adjusted pvalue(multiple correction),Term(Description),Ontology.

The list can be downloaded via the button on the bottom of the results panel.

Notes

Any error in format of the input files or parameters will lead to error in result,which can be fixed by changing the parameters or modifying the input files to recognized format.

References/Acknowledgements

1)Ritchie ME, Phipson B, Wu D, Hu Y, Law CW, Shi W and Smyth GK (2015). â€œlimma powers differential expression analyses for RNA-sequencing and microarray studies.â€ Nucleic Acids Research, 43(7), pp. e47.

2)Girke T (2015). systemPipeR: systemPipeR: NGS workflow and report generation environment. R package version 1.4.8, https://github.com/tgirke/systemPipeR.

3)CePa: Centrality-based pathway enrichment

4)https://plot.ly

5) H. Wickham. ggplot2: Elegant Graphics for Data Analysis. Springer-Verlag New York, 2009

6)Shiny/Rstudio

7)Wherry lab members
