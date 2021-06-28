# GIS Application in Finance

## 1. Guide to Github

Create and use a repository, Start and manage a new branch, Open and merge a pull request: [HERE](https://guides.github.com/activities/hello-world/)

## 2. Python Set Up: Anaconda [1]

### 2.1 Create and acticate virtual environment

Run the commands in the conda prompt.
```
conda create --prefix="/path/to/your/course/folder/envpygis"
conda activate "/path/to/your/course/folder/envpygis"
```

### 2.2 Install packages

Run the commands in the conda prompt. **Note** that once enter the virtual environment (by type ```conda activate```), then the packages will only be available in this virtual environment.
```
conda install pygeos --channel conda-forge
conda install numpy pandas matplotlib shapely geopandas -c conda-forge
conda install -c conda-forge nodejs
conda install -c conda-forge jupyterlab
conda install -c conda-forge rasterstats
conda install -c plotly plotly 
conda install --channel conda-forge esda
conda install geopy -c conda-forge
conda install contextily -c conda-forge
conda install mapclassify -c conda-forge
```
***P.S.*** Conda-forge ([HERE](https://conda-forge.org/)) is a community effort that provides conda packages for a wide range of software. By using ```--channel```, we ask the computer to download the file from conda-forge.

### 2.3 Open JupyterLab

Run the following commands in the conda prompt. This will open the virtual environment in your course folder. Or you can simply type ```jupyter lab``` in the anaconda prompt, and this will open the lab for the whole computer.
```
jupyter lab --notebook-dir="path/to/your/course/folder/"
```

### 2.4 Load a shape file

```
load_shapefile.txt
file_path = './lecture1/data/ne_10m_admin_0_countries.shp'
world = gpd.read_file(file_path)
world.plot(figsize=(10, 6))
```

### 2.5 Useful conda commands

Packages commands: lsit, search, install, uninstall, update

```
conda list                          #list all the packages
conda list --name myenv             #list all the packages in myenv
conda search scikit-learn           # search whether scikit-learn is available
conda install scikit-learn=0.23.1   #install sl version 0.23.1
conda uninstall scikit-learn        
conda update scikit-learn           #update
conda clean                         #remove useless packages
conda clearn -y --all               #delete all packages and cache
```

Environment commands: create, activate, deactivate, list, remove, open jupyter
```
#conda create --name [env name][python version][packages]
conda create -n myenv python=3.5                 #create myenv in python3.5
conda create --name myenv python=3.5 numpy scipy #create myenv in python3.5 and install 2 pkgs
conda create --name mybase --clone base          #clone base and create mybase

conda activate myenv              
conda deactivate                    
conda env list                     #list all env
conda remove --name myenv --all    #remove myenv

jupyter lab --notebook-dir="path/to/your/course/folder/"   #open jupyter lab in virtual env
```


## References
- [Python setup for GIS applications under Windows](https://gist.github.com/sebastianhohmann/4098cc6763b35f04317a850881af998a) [1]
- [Getting started with conda guide](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)
- [conda cheetsheat](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)


