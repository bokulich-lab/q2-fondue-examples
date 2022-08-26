# q2-fondue-examples
Materials accompanying q2-fondue article.

## Setup
To run the notebooks in `use_cases` we suggest you set up a conda environment as follows:

* Install [mamba](https://github.com/mamba-org/mamba) in the base environment:
```shell
conda install mamba -n base -c conda-forge
```
* Create and activate a conda environment with the required dependencies:
```shell
mamba create -yn fondue-pub \
   -c qiime2 -c conda-forge -c bioconda -c udst -c defaults \
   --file requirements.txt
```
```shell
conda activate fondue-pub
```
```shell
pip install \
    git+https://github.com/bokulich-lab/q2-coordinates.git \
    https://github.com/dib-lab/q2-sourmash/archive/master.zip
```
* Install sra-tools using the script provided in the [q2-fondue](https://github.com/bokulich-lab/q2-fondue) repository.
```shell
curl -sLH 'Accept: application/vnd.github.v3.raw' https://api.github.com/repos/bokulich-lab/q2-fondue/contents/install-sra-tools.sh > install-sra-tools.sh

chmod +x install-sra-tools.sh
bash install-sra-tools.sh

rm install-sra-tools.sh
```
* Ensure sra-tools are configured properly (see [original repo](https://github.com/bokulich-lab/q2-fondue#installation) for details):
```shell
vdb-config -i
```
* In case you need to configure a proxy server, run the following command 
(this can also be done using the graphical interface described above):
```shell
vdb-config --proxy <your proxy URL> --proxy-disable no
```
* Finally, install q2-fondue and refresh the QIIME 2 CLI cache:
```shell
pip install git+https://github.com/bokulich-lab/q2-fondue.git@5afa120cc8e017a1af6c1200a06326a2e08cc787

qiime dev refresh-cache
```
* Enable QIIME 2's Jupyter extension:
```shell
jupyter serverextension enable --py qiime2 --sys-prefix
```    

**Note:** Visualisation outputs of the Jupyter notebooks in `use_cases/` are best viewed in Jupyter Notebook.      

## Contact

In case of questions or comments feel free to raise an issue in this repository. 


## License

This repository  is released under a BSD-3-Clause license. See LICENSE for more details.
