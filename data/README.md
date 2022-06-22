# Datasets

This folder contains .pkl and .csv files of the HTE data from Ahneman, *et al*.  

## Getting the data

To unpickle the data:  

```python
import pickle

# Load in the DFT features
xy_pkl= open('./data/BH_CR_DFT.pkl', 'rb')
xy= pickle.load(xyDFT_pkl)
xs=xy.drop('yield', axis=1)
ys=xy['yield']
```

## Key

- `BH_CR_DFT`: The 120 DFT features from the original dataset  
- `BH_CR_numbers`: Each reaction is categorically encoded  
- `BH_CR_smiles`: Each reactant is encoded with its SMILES string  

## Notes

1. Control wells have been removed from the dataset  
2. Each dataset includes the label column `'yields'`  
3. `BH_CR_numbers` is very useful for both one-hot encoding and stratified CV  