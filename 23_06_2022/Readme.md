
 ## Counting Relative feature tightness against a PMI interrelation profile
 In this folder you can find a jupyter notebooks(23_06relative_feature_tightness[0-9]), where I count Relative feature tightness against a PMI interrelation profile. I have already splitted the dataset into 10 part. Therefore, for the train part using 90% of dataset and for the test part 10% of dataset. Repeating this process described below 10 times, using different 10% of dataset. The results are on display in RFT.pdf in folder 23_06_2022/images/RFT.pdf.
 
 *Process of counting RFT:*
 - Making feature pointwise mutual information profiles
 - Making feature pointwise KL divergence profile between COCONUT and ZINC
 - Sampling structures from COCONUT and ZINC datasets
 - Relative feature tightness against a PMI interrelation profile
 - Plotting a graph, these graphs are on display in PDF in folder 23_06_2022/images/RFT.pdf


*23_06themostfrequentfragment.ipynb*
- In the jupyter notebook 23_06themostfrequentfragment.ipynb I analyzed the most frequented combinations of fragments and also look at the Bits representing   these fragments. 




