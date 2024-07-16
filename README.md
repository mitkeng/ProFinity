# ProFinity: proton affinity prediction
A machine learning program for predicting proton affinities of small molecules and metabolites

#
### Introduction
ProFinity is a machine learning program for predicting proton affinities (PA) of various small molecules and metabolites. Since PA is a gas phase property, the amount of diverse experimental PA measurements available is limited, thus ProFinity can be practical for accurately predicting PA values for unknown chemicals within the interpolation limit.

Overall, ProFinity uses two neural network models:1) a model for predicting PA values and 2) a model for error correction. Ultimately, both models synergistically deliver error attenuated results. 
<br />

#
### Performance
<img align = "left" width="410" alt="focus" src="https://github.com/user-attachments/assets/1526387d-9520-4fea-9fa9-1bdcbc7d04be">
<img align = "center" width="410" alt="focus" src="https://github.com/user-attachments/assets/59fd4d1f-3ad5-45b1-b07d-f6d785965be6">

#
### Functionality
The program supports single logIE query or batch chemical logIE query. For single query, either a canonical SMILE or a CAS number is applicable. For batch query, either of the following csv file data layout is appropriate:

| SMILES|                              
|-------------|                             
|Cc1cccc(C)c1|                               
|n... |     

or

|CASE|
| ----|
| 108-38-3|
|n...|


Upon completion of a task a tabulated result like the table below is saved in a csv file.

|SMILE| PA|
|-----|----|
|C1=CNC(=O)NC1=O	|189.36111|
|n...|...|


#
### Requirement
Google account needed to access Google Colab notebook.

#
### Support
To create a small batch query csv input file *ad hoc*:
```twig
import pandas as pd

try:
  !touch small_batch.csv
except:
  pass

column_names=["SMILES"]
small_batch=pd.read_csv("small_batch.csv", names=column_names)
comp_list = #example: ["C(=O)=O", "O"]
small_batch['SMILES'] = comp_list
small_batch.to_csv("small_batch.csv", index=False)
```
#
### Limitations
ProFinity only supports chemicals containing the following atom types: H, He, B, C, N, O, F, P, S, Cl, Fe, As, Br, I, and Xe. The models have been trained on small molecules and metabolites, therefore it may significantly underperform for sizeable biomolecules. 

#
### Accessibility
 [<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">](https://colab.research.google.com/drive/1f-UWLOUJWi44j_hJ0BzzREleH-hZmaCL?usp=sharing) <code style="color : grey">to access the ProFinity platform.</code>
<img align = "right" width="100" alt="focus" src="https://github.com/user-attachments/assets/715704c6-5506-4b0c-9be5-897e5daa5820">

<br />

