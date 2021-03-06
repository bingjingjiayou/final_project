## Because some files are too large to be uploaded directly, my clinical data folder contains only part of the original data. I uploaded a separate copy of the differentially expressed genes in this file. My original data and data generated from analysis are put into Google drive, Google drive document 510 Final project contains two folders, the original data LIRI folder and the analysis data folder exported after analysis. Google drive link:https://drive.google.com/drive/folders/1MQhspwIbCDDrQtb8Tnzp_1LDLo2V3dUL

# Step 1:The processing data is in a format that can be analyzed by deseq2.

## 1，Download the data of phase II liver cancer patients from ICGC website. And upload to R, see documents Anno and Bnno.
![image](https://user-images.githubusercontent.com/89620829/144572867-0c16d01d-4b91-452d-b88d-32baceb815e0.png)

![image](https://user-images.githubusercontent.com/89620829/144572993-97fc9a23-97b6-47de-83d6-05f3d597aa3b.png)

## 2, Some of these data are selected, that is, whether the diagnosis age as the main variable is a high incidence period, covariate gender and family history. See documents Anno1 and Bnno1.
![image](https://user-images.githubusercontent.com/89620829/144573423-41748317-a0aa-495b-9c45-1fdc27a59e86.png)
![image](https://user-images.githubusercontent.com/89620829/144573497-57622d21-709d-44b7-ac63-6ae66a6fac11.png)

## 3, Because some patients in my data have been tested for many times and some have only been tested once, the data are processed and the first detection value is taken for analysis.

## 4, Adjust the length and width format, and turn donor_ ID becomes the first line. See Anno3.
![image](https://user-images.githubusercontent.com/89620829/144573604-cb4d3b39-ff53-4219-93b7-947e5dba14f6.png)

## 5, Since my count data is the data of all patients, I based on 106 donors of phase II patients_ ID is used to merge the number of cases in count, and only the data of 106 patients are taken. And adjust the file to the file Anno9 that can be analyzed by deseq2.
![image](https://user-images.githubusercontent.com/89620829/144573720-4f5e57df-2755-4ccc-a1c5-6c41752c432a.png)

# Step 2：Deseq2 analysis data

## 1, The processed data were analyzed with deseq2 to compare the expression differences of different genes in patients. According to the analysis results, there are 317 differential genes with P < 0.1, 252 differential genes with P < 0.05 and 171 differential genes with P < 0.05. See Figure P < 0.01.
![image](https://user-images.githubusercontent.com/89620829/144574004-4a17fa70-0058-40dc-91bd-4a4c64efee4d.png)

## 2, Thus, the log2 multiple change plot MA1 of the average standardized count of all samples in a given variable can be obtained. And the plot ma2 diagram after eliminating the noise related to the log2 multiple change of low count genes. See MA1 and MA2.
![image](https://user-images.githubusercontent.com/89620829/144574360-1bad7e68-4285-4dcf-a8a7-1467e22a0353.png)
![image](https://user-images.githubusercontent.com/89620829/144574527-d32ec357-26a8-4e0f-b7a6-15e41a7196b8.png)

 ## 3, Looking at the three normal distribution maps, we can see that the original adaptive distribution map is the best. See normal distribution diagram.
 ![image](https://user-images.githubusercontent.com/89620829/144577165-49ec853f-3b1a-496f-9e4c-e12a84abfb4f.png)
 
 ## 4, Check the reading count of a single gene across groups through the function plotcounts, specify the gene with the minimum p value, and make the following figure, as shown in Figure plot. It can be seen that there is no significant difference in the count of the minimum p value between the two groups.
 ![image](https://user-images.githubusercontent.com/89620829/144663007-18868062-01f3-45d9-b862-a10d0e731716.png)

## 5，Multifactor design: use the design formula containing additional variables to analyze the experiments with multiple factor influence counts, and analyze the log2 multiple change, P value and adjusted p value of variables other than the main variable.

## 6，Transform and visualize multivariable data. Firstly, the influence of transformation on square difference is analyzed, and three transformations are used, NTD, VSD and rld. The results show that the variance of rld transform is the smallest.
![image](https://user-images.githubusercontent.com/89620829/144665326-18a2e366-eb0f-47a1-831d-73e95e1f3d8c.png)
![image](https://user-images.githubusercontent.com/89620829/144665381-2a27ce1d-251a-4689-aca0-5bceb05e328d.png)
![image](https://user-images.githubusercontent.com/89620829/144665433-669deb43-3f47-466a-987e-3606831eaa54.png)

## 7,The data quality is evaluated by sample clustering and visualization, and the heat map of counting matrix is made. After analyzing various transformations to generate such heat maps, it can be seen from the previous data that my rld transformation variance is the smallest, so I only take the heat map generated by rld transformation.
 ![image](https://user-images.githubusercontent.com/89620829/144666246-870b3a20-f844-42d6-b9f4-a7c74125d1e5.png)

## 8，At the same time, the heat map of sample to sample distance is generated.
![image](https://user-images.githubusercontent.com/89620829/144679422-0015e20d-6489-4648-8c95-ee9e5a695cbd.png)

## 9，The principal component diagram of the sample is generated, and the PCA diagram related to the distance matrix is obtained, which visualizes the gender and family history of the two covariates of the experiment.The following figure shows the PCA diagram customized by using the ggplot function.Firstly, comparing the difference between the first main variable（donor_age_at_diagnosis） and the first covariate（donor_sex）, we can see that there is no obvious grouping. It shows that there is no difference between the two variables.
![image](https://user-images.githubusercontent.com/89620829/144679482-58be7eff-302a-4202-8baf-05aae3084785.png)

## Then compare the difference between the second main variable（donor_age_at_diagnosis） and the second covariate（cancer_history_first_degree_relative）, and there is no obvious grouping. It shows that there is no difference between the two variables.
![image](https://user-images.githubusercontent.com/89620829/144679531-7894d09f-aa03-4be8-914f-c17b73c00bc1.png)

# Step 3：Evaluation genes
 ## 1，  According to the query results, two of the six genes with the largest expression difference are related to the expression of other genes. They are up regulated in HEK293 cells (kidney fibroblasts) up known of TP53 [gene id = 7157] gene by RNAi.
![image](https://user-images.githubusercontent.com/89620829/144694418-0359b261-ac0a-4ddb-8eb7-69dd680f55dc.png)

## Further information retrieval and analysis of the two genes with search results found that:
## SPRR1B: down regulated gene expression in primary epithelial breast cancer cell cultures overexpressing E2F3 (ID = 1871] gene).It is also a gene that mediates the programmed death of epidermal cells. It also mediates the high expression of immune cytokines under some stimuli.
## RGR: it can down regulate the expression of MGMT [GeneID=4255] gene in glioma and increase the CCND1 in breast cancer [gene ID = 595].   Genes. Other studies have shown that this gene is related to biological light sensitivity.

## Therefore，according to the analysis results, I got 171 differentially expressed genes in P<0.01, and the most significant genes were found to be related to up regulation or down expression of cancer genes, such as breast cancer and neurocytoma. These genes are not only differentially expressed in the 2 stage of liver cancer, but may also mediate the expression of other cancer genes. There are also some genes that mediate cell fusion and conduction. 

# Step 4：Known Issues
## The main problems I have in this project are: 1. The processing of the original data is a little complicated, because the original data contains some data you don't need to remove. 2. After selecting the data, adjust it to a format suitable for deseq analysis. The type is also complex, and various format transformations are required. 3. The problems encountered in the process of analyzing the data are mainly caused by the characteristics of the data itself. For example, after comparison, it is found that my two covariates are not different from the main variable. 4. Many differentially expressed genes can not directly reflect the association with the disease, indicating that further research and analysis are needed.

# Step 5：Conclusions：It can be seen from my PCA chart that there is no significant grouping difference between my main variable (donor_age_at_diagnosis) and covariate (donor_sex), and there is no significant difference between the main variable (donor_age_at_diagnosis) and covariate (cancer_history_first_degree_relative), It shows that the data of other groups are not affected by gender and family history, and their gene differential expression is basically similar.



