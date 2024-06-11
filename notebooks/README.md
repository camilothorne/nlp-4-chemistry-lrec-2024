### Installation instructions

The Jupyter notebooks in this directory have been tested on Python 3.7 (`T5Chem_demo.ipynb`) and 3.9+ (all others). In order for them wo work
properly, some prior steps are necessary. These instructions assume that you pre-installed the Miniconda or Anaconda package managers 
on your (local) host machine, together with Jupyter.

For the notebooks to work, you need to open your terminal (I'm assuming you are using a Unix based host, be it MacOSX or Linux) 
create two **empty** (fresh: don't re-use existing environments, unless you like debugging dependency conflicts!) `conda` virtual 
environments as follows:
```bash
conda create --name <env-name> python=<version-number>
```

Once created, we need to create Jupyter kernels, so that Jupyter can communicate with eech such virtual environment:
```bash
conda activate <env-name>
conda install ipykernel
python -m ipykernel install --name Chem_<env-name> --user # links the kernel to the underlying Python virtual environment
conda deactivate
```

And... that's it. When you (re)start Jupyter, you'll be able to see and select these two new kernels in the kernel menu.

Additionally, you'll see that some of the notebooks expect some custom Python libraries under `tools`. These need to be manually
downloaded from the Google Drive (see the instructions and URL in `tools`) and copied over onto the `tools` directory.
Likewise, you'll need to manually download the model checkpoints they refer to, and move them to `models`.

**NOTE:** `T5Chem_demo.ipynb` will only work on Python 3.7, due to some dependencies to early versions of the `transformers` library.
