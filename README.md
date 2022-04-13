# Fatty-acid-impact-calculations

Downloading dependencies. 

```sh
# create new conda environment
conda create -n impacts -c cantera -c conda-forge python numpy scipy pyyaml cantera scikit-build cmake ninja matplotlib jupyter numba

# activate the environment
conda activate impacts

# Install ImpactAtmosphere v4.2.7
git clone https://github.com/Nicholaswogan/ImpactAtmosphere
cd ImpactAtmosphere
git checkout 2528c64c101bbde56db1886c6b59ca3df7cd05f0
python -m pip install --no-deps --no-build-isolation .
```

Navigate to this directory, and open the Jupyter Notebook with

```sh
jupyter notebook Fatty_acid_impact_calculations.ipynb
```

Results are stored in the `results` directory. Loading the results can be done with

```python
import yaml
import pickle

def load_results(f1, f2):
    f = open(f1,'r')
    meta = yaml.load(f,Loader=yaml.Loader)
    f.close()
    f = open(f2,'rb')
    s = pickle.load(f)
    f.close()
    return meta, s
    
meta, s = load_results("meta_data_filename.yaml", "pickle_filename.pkl")
```
