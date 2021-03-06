# Creating a Conda environment for GEO4902


## Download Miniconda 
We will use Miniconda as it is a smaller version of Anaconda. You will have the same advantages as with Anaconda. It comes with a complete Python distribution and lets you create isolated _environments_ that don't affect anything else. 

You can follow the steps as here described by the [CodeRefinery](https://coderefinery.github.io/installation/conda/).

1. Open your terminal (e.g within VS Code)
2. Download the most recent version of Miniconda installer 
   - [for Linux](https://docs.conda.io/en/latest/miniconda.html#linux-installers)
   - [for Windows](https://docs.conda.io/en/latest/miniconda.html)
   - [for macOS](https://docs.conda.io/en/latest/miniconda.html)
3. [Verify you installer hashes](https://docs.conda.io/projects/conda/en/latest/user-guide/install/download.html#hash-verification)
4. In the terminal window run (for Miniconda):
   - Linux: 

```
$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

```
Go to the location where you downloaded the Miniconda installer and check the integrity of the downloaded file with SHA-256:
```
$ sha256sum ./Miniconda3-latest-Linux-x86_64.sh
1ea2f885b4dbc3098662845560bc64271eb17085387a70c2ba3f29fff6f8d52f  ./Miniconda3-latest-Linux-x86_64.sh
```  
Compare the above hash value with the [official Hashes](https://docs.conda.io/en/latest/miniconda.html) for Miniconda. To install Miniconda on Linux, run:
```
$ bash ./Miniconda3-latest-Linux-x86_64.sh 

```
   - Windows: Double-click the `.exe` file.
   - macOS: 

Download the file [Miniconda3-latest-MacOSX-x86_64.sh](https://docs.conda.io/en/latest/miniconda.html) and verify the integrity of the download.
```
$ sha256sum -a 256 Miniconda3-py39_4.9.2-Linux-x86_64.sh
``` 
Compare the above hash value with the official Hashes for Miniconda. To install Miniconda on Linux, run:
```
$ bash Miniconda3-latest-MacOSX-x86_64.sh
```

5. Follow the prompts on the installer screen.
6. To make changes take effect, close and re-open your terminal window
7. Test you installation: In the terminal run `conda list`

(The above information is taken from the [conda docs installation guide](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html). If you have trouble you can look up the download for your OS on the Miniconda documentation. The latest Miniconda version are found [here](https://docs.conda.io/en/latest/miniconda.html).)



## Creating an exisiting virtual environment
The following steps are taken from the CodeRefinerey workshop software [installation instructions](https://coderefinery.github.io/installation/#), specifically [creating a conda envrionment for CodeRefinerey workshops](https://coderefinery.github.io/installation/conda-environment/#conda-environment).

1. If you have not, activate `conda` in Miniconda first using `conda activate`.
2. Run the following command
```
$ conda env create -f https://raw.githubusercontent.com/franzihe/GEO4902/main/environment_geo4902.yml

```
3. Make sue you see "geo4902" in the output when you ask for a list of all available environments:
```
$ conda env list
```

## Activate the `geo4902` envrionment
```
$ conda activate geo4902
```
## Deactivate the `geo4902` envrionment
```
$ conda deactivate

```
## Adding new packages 
```
$ conda install NEW_PACKAGE
```

## Remove the `geo4902` envrionment
```
$ conda remove --name geo4902 --all
```
