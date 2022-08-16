- Generated random dataset of COCONUT and ZINC

- firstly, shuffled the whole dataframe and then splitted into 10 equal parts
- by using following:
- suppl_csv = suppl_csv.sample(frac=1).reset_index(drop=True)
- df_split = np.array_split(suppl_csv, 10)
- reaching the subsets by: df_split[0] or df_split[1] etc.


- Performed basis analysis of COCONUT and ZINC data 

- Compared these profiles

