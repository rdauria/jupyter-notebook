# h2jupynb: Jupyter notebook launcher script for the Hoffman2 Cluster

*Jupiter notebook, formerly known as IPython notebook*


Launch an interactive session on the a compute node of the Hoffman2 cluster via the UGE scheduler from your local computer and displayes it on your local browser. 

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

h2jupynb [-u <Hoffman2 user name>] [-t <time - integer number of hours>] [-m <memory - integer number of GB>] [-e <parallel environment: 1 for shared, 2 for distributed>] [-s <number of slots>] [-v <python-version>] [-o <run on group owned nodes: yes/no>] [-x <run on an exclusively reserved node: yes/no>]  [-a <CPU-type>] [-d <directory from which the jupyter NB/lab will start>] [-p <port number>] [-g <run on a gpu node: yes/no>] [-c <gpu-card-type>] [-l <cuda-version>]

If no arguments are given to this script it is assumed that:
	 your Hoffman2 user name is the same as on your client machine
	 the time duration for your session is of 2 hours
	 the parallel environment is shared
	 the memory per slot for your session is of 1GB
	 the number of slots for your session is of 1
	 the python version for your notebook is 2.7.13
	 the port on which the server is started is 8789
	 the starting directory on Hoffman2 is your $HOME
	 use GPU? default is no
	 GPU type default is P4 (if -g = yes)
	 CUDA version 9.1 (if -g = yes)
	 not running on owned nodes
	 not running in exclusive mode
	 no specific CPU selected (see ARCH in qhost output)

	 python versions currently available are: 2.7.13, 2.7.16, 3.6.1, 3.7.0, 3.7.2
	 or: anaconda2 and anaconda3
	 python versions: 2.7.3 or 3.4 are available but deprecated.

	 cuda versions currently available are: 7.0, 7.5, 8.0 and 9.1

```
	 
The script can be run either by issuing:

`./h2jupynb`

or by issuing:

`python h2jupynb`

or:

`python3 h2jupynb`
