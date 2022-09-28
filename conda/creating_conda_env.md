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
$ conda env create -f environment_geo4902.yml

```
> **_NOTE:_** You need to have downloaded the [environment file](./environment_geo4902.yml) located in the GEO4902/conda directory or create your own conda environment with the package listed in the [environment file](./environment_geo4902.yml). (Package versions can be found at the end of the document.)
> 
1. Make sure you see "geo4902" in the output when you ask for a list of all available environments:
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

## Package versions currently used
In GEO4902, we currently use the following packages as listed in the [environment file](./environment_geo4902.yml) with versions:


<p style="background:black">
<code style="background:black;color:white"> >> python: version 3.10.6 <br>
>> nc_time_axis: version 1.4.1 <br>
>> zarr: version 2.12.0 <br>
>> xarray: version 2022.6.0 <br>
>> matplotlib: version 3.5.3 <br>
>> cftime: version 1.6.1 <br>
>> dask: version 2022.9.0 <br>
>> cmcrameri: version 1.4 <br>
>> scipy: version 1.9.1 <br>
>> intake: version 0.6.6 <br>
>> seaborn: version 0.12.0 <br>
>> xesmf: version 0.3.0 <br>
>> cartopy: version 0.21.0 <br>
>> Selected Jupyter core packages... <br>
>> IPython          : 8.5.0 <br>
>> ipykernel        : 6.15.2 <br>
>> ipywidgets       : 8.0.2 <br>
>> jupyter_client   : 7.0.6 <br>
>> jupyter_core     : 4.11.1 <br>
>> jupyter_server   : not installed <br>
>> jupyterlab       : not installed <br>
>> nbclient         : 0.6.8 <br>
>> nbconvert        : 7.0.0 <br>
>> nbformat         : 5.4.0 <br>
>> notebook         : 6.4.12 <br>
>> qtconsole        : 5.3.2 <br>
>> traitlets        : 5.3.0 <br>
</code>
</p>


To check which versions you have installed run the following in a Jupyter notebook.
```
from platform import python_version
import nc_time_axis
import zarr 
import xarray as xr
import matplotlib as mpl
import cftime
import dask as da
import cmcrameri as cm
import scipy
import intake
import seaborn
import xesmf
import cartopy as crs

print('python: version {}'.format(python_version()))
print('nc_time_axis: version {}'.format(nc_time_axis.__version__))
print('zarr: version {}'.format(zarr.__version__))
print('xarray: version {}'.format(xr.__version__))
print('matplotlib: version {}'.format(mpl.__version__))
print('cftime: version {}'.format(cftime.__version__))
print('dask: version {}'.format(da.__version__))
print('cmcrameri: version {}'.format(cm.__version__))
print('scipy: version {}'.format(scipy.__version__))
print('intake: version {}'.format(intake.__version__))
print('seaborn: version {}'.format(seaborn.__version__))
print('xesmf: version {}'.format(xesmf.__version__))
print('cartopy: version {}'.format(crs.__version__))

!jupyter --version

```
