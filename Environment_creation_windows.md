conda create -n DSTIlabs python=3.7
conda activate DSTIlabs
conda info
conda env list 
conda update python
conda update --all --yes
conda install ipykernel
ipython kernel install --user --name=DSTIlabs
jupyter notebook --ip=0.0.0.0 --no-browser

pip install numpy
pip install pandas
pip install seaborn
pip install scikit-learn
pip install matplotlib

conda update --all --yes