## Section 1:Update
* After downloading the data, I selected the data I needed.And is converting it into a format that can be analyzed in DEseq2.The scripts I use are in the scripts folder.
![image](https://user-images.githubusercontent.com/89620829/144680410-457efff8-9626-4a85-9db2-6564651d2ec3.png)
![image](https://user-images.githubusercontent.com/89620829/144680452-716dd6d6-f151-466c-a886-d4c2ce081585.png)



## Section 2: Next Steps.
* Because I spend a lot of time processing data, I will talk about differential expression comparison and making volcano map. Next, the content of milestone 2, several variables and more detailed tumor gene expression analysis.


## Section 3: Data.  Not due by Milestone 1, but I'll address.



## Section 4: Known Issues. 
* 1. After downloading the data, I selected the data I needed. When I changed the length width format and folded the data, I found that the data was DBL. There were some problems with the folded data, so I converted DBL to int format. 
* 2. After data folding, I found that the number of genes is more than 100000, which is unreasonable. Therefore, after I changed the code, I found that some samples were measured repeatedly, so there may be two or more data for the same gene in the same sample, but some samples are measured only once, so it can not be guaranteed that all samples are measured multiple times, and the measurement time in the back is not necessarily the same. Therefore, I only compare the first measurement of all samples. So I'm trying to take the first data from multiple measurements and then output the data.
* 3. Because my sample data processing takes too much time and is still processing the last step, I need to extend the time. After processing, I will carry out the next analysis.
