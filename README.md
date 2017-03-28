# h2ipynb: Jupyter notebook launcer script for the Hoffman2 cluster

*Jupiter notebook, formerly known as IPython notebook*


Launch an interactive session on the a compute node of the Hoffman2 cluster via the UGE scheduler from your local computer and displayes it on your local browser. 

The script (adapted from: https://github.com/pyHPC/ipynbhpc) performs the following steps:

1. connectes to a login node of the Hoffman2 cluster
2. launches an interactive session on one (or more) compute node (number of cores is requestable)
3. loads the python module that you have requested (or else uses the 2.7.3 default version)
4. starts the notebook server on a given port (requestable)
5. back on your machine, starts an ssh-port-forwarding to the cluster to the given notebook port
6. opens your default web browser on your local machine 

Your notebook then should appear on your default web browser on your local machine.

To display usage issue:

`h2ipynb --help`

You will get:

```
h2ipynb [-u <Hoffman2 user name>] [-t <time in hours>] [-m <memory in GB>] [-s <number of slots>] [-v <python-version>] [-p <port>] [-d <dir>]
 
 If no arguments are given to this script it is assumed that:

	 your Hoffman2 user name is the same as on your client machine
	 the time duration for your session is of 2 hours
	 the memory per slot for your session is of 1GB
	 the number of slots for your session is of 1
	 the python version for your notebook is 2.7.3
	 the port on which the server is started is 8789
	 the starting directory on Hoffman2 is your $HOME

	 python versions currently available are 2.7.3 or 3.4
```
	 
The script can be run either by issuing:

`./h2ipynb`

or by issuing:

`python h2ipynb`

or:

`python3 h2ipynb`