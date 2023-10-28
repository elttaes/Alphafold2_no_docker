# Alphafold2_no_docker 2023-10-16
### **if anaconda not installed**
``` bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && bash Miniconda3-latest-Linux-x86_64.sh
```
### **Alphafold2 v2.3.2 environment**
``` bash
git clone https://github.com/google-deepmind/alphafold
cd alphafold
conda create -n alphafold python=3.10
conda activate alphafold
conda install -c "nvidia/label/cuda-11.8" cuda-nvcc
conda install -c "nvidia/label/cuda-11.8.0" cuda-toolkit

conda install openmm=7.7.0 pdbfixer -c conda-forge
conda install kalign3 -c bioconda
pip3 install -r requirements.txt
pip3 install --no-dependencies ../alphafold
pip3 install pyopenssl==22.0.0

mkdir -p alphafold/alphafold/common
wget https://git.scicore.unibas.ch/schwede/openstructure/-/raw/7102c63615b64735c4941278d92b554ec94415f8/modules/mol/alg/src/stereo_chemical_props.txt
cp -f alphafold/stereo_chemical_props.txt alphafold/alphafold/common
mkdir -p ~/miniconda3/envs/alphafold/lib/python3.10/site-packages/alphafold/common/
cp -f stereo_chemical_props.txt ~/miniconda3/envs/alphafold/lib/python3.10/site-packages/alphafold/common/
pip install mock

pip install --upgrade "jax[cuda11_pip]" -f https://storage.googleapis.com/jax-releases/jax_cuda_releases.html

```
