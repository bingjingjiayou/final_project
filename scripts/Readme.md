# Step 1:The processing data is in a format that can be analyzed by deseq2.

## 1，I downloaded the data of phase II liver cancer patients from ICGC website. And upload to R, see documents Anno and Bnno.
![image](https://user-images.githubusercontent.com/89620829/144572867-0c16d01d-4b91-452d-b88d-32baceb815e0.png)

![image](https://user-images.githubusercontent.com/89620829/144572993-97fc9a23-97b6-47de-83d6-05f3d597aa3b.png)

## 2、 Some of these data are selected, that is, whether the diagnosis age as the main variable is a high incidence period, covariate gender and family history. See documents Anno1 and Bnno1.
![image](https://user-images.githubusercontent.com/89620829/144573423-41748317-a0aa-495b-9c45-1fdc27a59e86.png)
![image](https://user-images.githubusercontent.com/89620829/144573497-57622d21-709d-44b7-ac63-6ae66a6fac11.png)

## 3、 Because some patients in my data have been tested for many times and some have only been tested once, the data are processed and the first detection value is taken for analysis.

## 4、 Adjust the length and width format, and turn donor_ ID becomes the first line. See Anno3.
![image](https://user-images.githubusercontent.com/89620829/144573604-cb4d3b39-ff53-4219-93b7-947e5dba14f6.png)

## 5、 Since my count data is the data of all patients, I based on 106 donors of phase II patients_ ID is used to merge the number of cases in count, and only the data of 106 patients are taken. And adjust the file to the file Anno9 that can be analyzed by deseq2.

## 1、 The processed data were analyzed with deseq2 to compare the expression differences of different genes in patients. According to the analysis results, there are 317 differential genes with P < 0.1, 252 differential genes with P < 0.05 and 171 differential genes with P < 0.05. See Figure P < 0.01.

## 2、 Thus, the log2 multiple change plot MA1 of the average standardized count of all samples in a given variable can be obtained. And the plot ma2 diagram after eliminating the noise related to the log2 multiple change of low count genes. See MA1 and ma2.
