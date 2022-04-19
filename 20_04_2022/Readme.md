
**18_04heavyatoms.ipynb** 
- firstly, used: l.GetNumHeavyAtoms() to get the number of heavy atoms in molecule
- made boxplot and basic statistics using seaborn library and .describe()
- both of these made for ZINC and COCONUT data
- For COCONUT data getting: mean 34.161340
- For ZINC data getting: mean 28.009868

**18_04splitdataset.ipynb** 
- suppl_csv = suppl_csv.sample(frac=1).reset_index(drop=True)
- df_split = np.array_split(suppl_csv, 10)
