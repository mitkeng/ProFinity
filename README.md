# ProFinity: proton affinity prediction
A machine learning program for predicting proton affinities of small molecules and metabolites
![PA_uncorrected](https://github.com/user-attachments/assets/1526387d-9520-4fea-9fa9-1bdcbc7d04be)
![PA_corrected](https://github.com/user-attachments/assets/59fd4d1f-3ad5-45b1-b07d-f6d785965be6)


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
comp_list = #list of compounds -> ["C(=O)=O", "O"]
small_batch['SMILES'] = comp_list
small_batch.to_csv("small_batch.csv", index=False)
```
#
### Limitations
ProFinity only supports chemicals containing the following atom types: H, He, B, C, N, O, F, P, S, Cl, Fe, As, Br, I, and Xe. The models have been trained on small molecules and metabolites, therefore it may likely underperform for sizeable biomolecules. 

#
### Accessibility
 [<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">](https://colab.research.google.com/drive/1f-UWLOUJWi44j_hJ0BzzREleH-hZmaCL?usp=sharing) <code style="color : grey">to access the ProFinity platform.</code>
<img align = "right" width="100" alt="focus" src="https://github.com/mitkeng/efficION/assets/97419520/dba56f1a-cce9-434f-b1c0-7ef836041810">


<br />

