
*Removing duplicates, creation csv to easily acces the data*

**ZINC_analysis_07-04.ipynb**:

Removing duplicates across sampled ZINC substances, exactly 10 substances with identical first INCHIKEY part. 

Creating new csv with ZINC substances, containing Zinc_id, Smiles, MW, logP, Inchi(Inchi) and Inchikey first part (Inchi_s). Naming it ZINCFINAL.csv (379 012) substances.

**COCO_to_CSV.ipynb**: 

Creating new csv containg COCONUT data. 'MW': db_mw, 'logP':db_logP, 'Smiles': db_smiles, 'Inchi': db_inchikey, 'coconut_id': db_COCONUT_id. Naming csv COCOALL.csv. (405 000 substances). Then deleting approx. 20 000 duplicates by inchi first part getting 386 297 substances. Naming the csv COCOFINAl.csv.

 **ECFP_11_04.ipynb:**
 
 Creating fingerprints for COCOFINAL.csv and ZINCFINAL.csv using 
-   Radius 2, lenght 2048
-   fp = AllChem.GetMorganFingerprint(mol, 2, nBits=2048)
-   fp.GetOnBits()
