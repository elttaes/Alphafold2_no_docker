# Alphafold2_no_docker 2023-10-16
### **if anaconda not installed**
``` bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && bash Miniconda3-latest-Linux-x86_64.sh
```
### **Alphafold2 v2.3.2 environment**
``` bash
git clone https://github.com/google-deepmind/alphafold
cd alphafold
conda create -n alphafold2 python=3.10
conda activate alphafold2
conda install openmm=7.7.0 pdbfixer -c conda-forge 
pip3 install -r ./alphafold/requirements.txt
pip3 install --no-dependencies ./alphafold
pip3 install pyopenssl==22.0.0

mkdir -p alphafold/alphafold/common
cp -f alphafold/stereo_chemical_props.txt alphafold/alphafold/common
mkdir -p /opt/conda/lib/python3.10/site-packages/alphafold/common/
cp -f stereo_chemical_props.txt /opt/conda/lib/python3.10/site-packages/alphafold/common/

pip install --upgrade --no-cache-dir jax==0.3.25 jaxlib=0.3.25 -f https://storage.googleapis.com/jax-releases/jax_cuda_releases.html
pip install mock
```
