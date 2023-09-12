# h2jupynb: Jupyter notebook launcher script for the Hoffman2 Cluster

*Jupiter notebook, formerly known as IPython notebook*


Launch an interactive session on the a compute node of the Hoffman2 Cluster via the GE scheduler from your local computer and displayes it on your local browser. 

The script (adapted from: https://github.com/pyHPC/ipynbhpc) performs the following steps:

1. connectes to a login node of the Hoffman2 cluster
2. launches an interactive session on one (or more) compute node (number of cores is requestable)
3. loads the python module that you have requested (or else uses the 2.7.13 default version)
4. starts the notebook server on a given port (requestable)
5. back on your machine, starts an ssh-port-forwarding to the cluster to the given notebook port
6. opens your default web browser on your local machine 

Your notebook then should appear on your default web browser on your local machine.

To display usage issue:

`h2jupynb --help`

You will get:

```
Usage:

h2jupynb [-u <Hoffman2 user name>] [-v <python-version>] 
         [-t <time, integer number of hours>] [-m <memory, integer number of GB per core>] 
         [-e <parallel environment: 1 for shared, 2 for distributed>] [-s <number of slots>] 
         [-o <run on group owned nodes: yes/no>] [-x <run on an exclusively reserved node: yes/no>]  
         [-a <CPU-type>] [-d <path to directory from which the jupyter NB/lab will start>] 
         [-g <run on a gpu node: yes/no>] [-c <gpu-card-type>] [-l <cuda-version>] 
         [-p <port number>]  [-j <conda virtual environment name>]
         [-k <path/to/python/virtual-env>] 
         [-b <comma separated list of environmental modules>]

If no arguments are given to this script it is assumed that:

	 your Hoffman2 user name is the same as on your client machine
	 the time duration for your session is of 2 hours
	 the parallel environment is shared
	 the memory per slot for your session is of 1GB
	 the number of slots for your session is of 1
	 the python version for your notebook is 3.9.6
	 the port on which the server is started is 8789
	 the starting directory on Hoffman2 is your $HOME
	 use GPU? default is no
	 GPU type default is RTX2080Ti (if -g yes)
	 CUDA version 10.2 (if -g yes)
	 not running on owned nodes
	 not running in exclusive mode
	 no specific CPU selected (see "ARCH" in output of "qhost")

	 Python versions currently available are: 2.7.18, 3.7.3, 3.9.6,
	 anaconda3/2020.07, anaconda3 (2020.11), anaconda3/2021.11,
	 anaconda3/2022.05, anaconda3/2023.03 

	 Architectures (CPUs) currently publicly available: see output of qhost
	 to request a specific architecture, e.g., intel-gold*: -a intel-gold\\*

	 Cuda versions currently available are: 9.2, 10.0, 10.2, 11.0

	 GPU cards currently publicly available are: P4, RTX2080Ti, V100

	 Environmental modules to be loaded as a comma (no space) list
	 (e.g.: gsl/2.6, or gsl,curl/7.70.0)

	 Conda virtual environment - assumes a version of anaconda3 is requested
	 (e.g.: treemix)

	 Python virtual environment - assumes a version of python (not anaconda3)
	 is requested (e.g.: \$HOME/PATH/TO/MYPYTHONENV)

	 **Should you specify non existing parameters default values will be assumed**

```
	 
The script can be run either by issuing:

`./h2jupynb`

or by issuing:

`python h2jupynb`

or:

`python3 h2jupynb`
