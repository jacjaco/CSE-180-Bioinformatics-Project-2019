# CSE-180-Bioinformatics-Project-2019
Differential  Gene Expression  for Varying  Cell Types
  __(Group Project Members: Jose Zaragoza, Allen Le, Jacqueline Olness)__
  
  
*Note to the user:  This pipeline has been developed with the notion that pre-processing of the series matrix-data has already been completed. For this project, the pre-processing of the data was done by a member of our team (Allen Exce-Le). We list the pre-processing procedure for changes to the reference database used in our pipeline: 

Pre-Processing Data Matrix
1.	Open the .txt file in excel
2.	Change the sample names to its corresponding cell type name, making sure to indicate the replicate number
3.	Remove rows corresponding to gene names that show as ‘null’ in the gene symbol column.
4.	Replace the gene reference ID with the names of the genes, referencing NCBI, ABI Human Genome Survey Microarray Version 2.





Pipeline Overview:
1.	Imports required packages (seaborn, numpy, pandas, matplotlib.pyplot, xlrd)
2.	Assumes that pre-processing has been completed in excel and the ‘genome_library.xlsx’ file is uploaded into the script.
3.	Print the cell type library and genes in the pre-up-loaded data-set for the user
a.	Output: Cell Type Library
4.	Cell Type Buttons for User to Select are printed, and the user’s inputs are placed inside a list (includes replicates)
a.	Input: User Selected Cell Types: User must select at least one cell type
5.	Stores these cell types in a list called: tissue_choices=[ ]
6.	Extract cell type columns based on “Cell Type Input” 
a.	Output=Tissue_matrix #Corresponding to Cell Types Chosen
7.	Append gene name (as a list) to the dataset matrix
a.	Output=updated_matrix #Gene names with cell types corresponding to choices by the user.
8.	Identify 16 max values for each of the cell types you’ve chosen uniquely and store in a list. 
9.	Determine the genes corresponding to these max 16 values
10.	Find the average expression across all cell types for a given gene
11.	Use the average to normalize the top 16 genes
12.	Find the difference between the max and min for the max genes, and use this difference as a standard for a threshold.
13.	A small difference indicates genes that are similar in a “high” threshold
14.	FIRST OUTPUT: Top 8 genes corresponding to the top 8 genes
15.	Remove 8 of the maximum averages differences that are below a “low” threshold for any of the five cell types.
a.	Heuristics in the fields of differential analysis state that we should examine p-values < 0.05, or t-tests, or statistical distributions to establish gene expression thresholds. However, since we are only interested in a rapid prototyping of gene expression, we created our own threshold. 
16.	Output: Comparative Heat Map
