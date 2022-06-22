# Datasets

This folder contains .pkl and .csv files of the HTE data from Ahneman, *et al*.  

## Unpickling the data

```python
import pickle

# Load in the DFT features
xy_pkl= open('./data/BH_CR_DFT.pkl', 'rb')
xy= pickle.load(xyDFT_pkl)
xs=xy.drop('yield', axis=1)
ys=xy['yield']
```

## Key

- `BHAmDataset_ControlRemoved_Numbered`: Reactants are encoded by SMILES string adn categorically encoded  
- `BH_CR_DFT`: The 120 DFT features from the original dataset  
- `BH_CR_numbers`: Each reaction is categorically encoded  
- `BH_CR_smiles`: Each reactant is encoded with its SMILES string  

## Notes

- Control wells have been removed from the dataset  
- Each dataset includes the label column `'yields'`  
- `BH_CR_numbers` is very useful for both one-hot encoding and stratified CV:  

```python
# To load in indices by compound number for a CV iterator or one-hot encoding
xNum_pkl= open('./data/BH_CR_numbers.pkl', 'rb')
xNum= pickle.load(xNum_pkl).drop('yield', axis=1)
```
