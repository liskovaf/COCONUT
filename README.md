# Feature interrelation profiling 
Feature interrelation profiling of natural products and comerically available compounds using COCONUT and ZINC dataset
# Step by step
## 01_11_2021
Coconut database analysis from sdf file 
- downloaded COCONUT database from https://coconut.naturalproducts.net/download in SDF format
- made a dataframe with molecular weights and logP values of COCONUT data
- conducted basic analasis of COCONUT data: created graphs of logP and molecular weights values

## 10_11_2021
ZINC sampling
zinc_database1.ipynb From ZINC database extracting substances that are similiar to the COCONUT data
ZINC_analysis1.ipynb Analysing ZINC data

## 14_04_2022
Removing duplicates, creation csv to easily acces the data
ZINC_analysis_07-04.ipynb:
Removing duplicates across sampled ZINC substances, exactly 10 substances with identical first INCHIKEY part.
Creating new csv with ZINC substances, containing Zinc_id, Smiles, MW, logP, Inchi(Inchi) and Inchikey first part (Inchi_s). Naming it ZINCFINAL.csv (379 012) substances.
COCO_to_CSV.ipynb:
Creating new csv containg COCONUT data. 'MW': db_mw, 'logP':db_logP, 'Smiles': db_smiles, 'Inchi': db_inchikey, 'coconut_id': db_COCONUT_id. Naming csv COCOALL.csv. (405 000 substances). Then deleting approx. 20 000 duplicates by inchi first part getting 386 297 substances. Naming the csv COCOFINAl.csv.
ECFP_11_04.ipynb:
Creating fingerprints for COCOFINAL.csv and ZINCFINAL.csv using
Radius 2, lenght 2048
fp = Chem.GetMorganFingerprintAsBitVect(molecule, 2, nBits=2048, bitInfo=bitinfo)
list(fp.GetOnBits())) bitinfo
Saving ECFP to ZINCECFP.csv
UPDATE: ECFP_15_04.ipynb: Added: ECFP of coco data - COCOEFCP.csv Deleted bitinfo (even in zincecfp.csv), left just ECFP and bitset

## 20_04_2022
18_04heavyatoms.ipynb
Firstly, used: l.GetNumHeavyAtoms() to get the number of heavy atoms in molecule
made boxplot and basic statistics using seaborn library and .describe()
both of these made for ZINC and COCONUT data
For COCONUT data getting: mean 34.161340
For ZINC data getting: mean 28.009868

## 19-05-2022
Generated random dataset of COCONUT and ZINC
firstly, shuffled the whole dataframe and then splitted into 10 equal parts
by using following:
suppl_csv = suppl_csv.sample(frac=1).reset_index(drop=True)
df_split = np.array_split(suppl_csv, 10)
reaching the subsets by: df_split[0] or df_split[1] etc.
Performed basis analysis of COCONUT and ZINC data
Compared these profiles

## 23_06_2022
Counting Relative feature tightness against a PMI interrelation profile
In this folder you can find a jupyter notebooks(23_06relative_feature_tightness[0-9]), where I count Relative feature tightness against a PMI interrelation profile. I have already splitted the dataset into 10 part. Therefore, for the train part using 90% of dataset and for the test part 10% of dataset. Repeating this process described below 10 times, using different 10% of dataset. The results are on display in RFT.pdf in folder 23_06_2022/images/RFT.pdf.

Process of counting RFT:

Making feature pointwise mutual information profiles
Making feature pointwise KL divergence profile between COCONUT and ZINC
Sampling structures from COCONUT and ZINC datasets
Relative feature tightness against a PMI interrelation profile
Plotting a graph, these graphs are on display in PDF in folder 23_06_2022/images/RFT.pdf
23_06themostfrequentfragment.ipynb

In the jupyter notebook 23_06themostfrequentfragment.ipynb I analyzed the most frequented combinations of fragments and also look at the Bits representing these fragments.

## 07_07_2022
Updated previous jupyter noteboks in file 23_06_2022:
Added ROC curves
You can find result images of ROC curves in the file: images
In folder fragments you can find preproccesing of COCONUT and ZINC fragments using funcition: fip.chem.rdmol2morgan_feature_smiles

## 10_08_2022

Creation of RFT profiles using ECFP-liek fragments with radius 2

## 17_08_2022
Looking at the most frequent fragments in COCONUT dataset compared to ZINC dataset


## 28_03_2023
Adding 10 RFT profiles into one graph, adding visually nicer MW and log P graphs, looking at the most frequent fragments in COCONUT and ZINC dataset

# Workflow of this work: 
![cross-validace (2)](https://user-images.githubusercontent.com/61705542/231712897-7471c915-236a-4f48-afe1-d7f68d0d15bb.svg)


