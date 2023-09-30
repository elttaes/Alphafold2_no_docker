# Alphafold2_no_docker 2023-09-30
### **if anaconda not be install**
``` bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && bash Miniconda3-latest-Linux-x86_64.sh
```
### **Alphafold2 v2.3.2 environment**
``` bash
git clone https://github.com/google-deepmind/alphafold
cd alphafold
conda create -n alphafold2 python=3.9
conda activate alphafold2
conda install -y -c conda-forge openmm cudatoolkit pdbfixer
conda install -y -c bioconda hmmer hhsuite kalign2
pip install -r requirment.txt
pip install --upgrade --no-cache-dir jax==0.4.14 jaxlib==0.4.14 -f https://storage.googleapis.com/jax-releases/jax_cuda_releases.html
pip install mock
```
