<title>h2ipyntbk: Jupyter IPython notebook launcer script for the Hoffman2 cluster</title>

Launch an interactive session on the a compute node of the Hoffman2 cluster via the UGE scheduler from your local computer. The script (adapted from: https://github.com/pyHPC/ipynbhpc) connectes to a login node of the Hoffman2 cluster, launches an interactive session on one (or more) compute node, loads the python/2.7.3 (more python versions to be supported in the future), starts the notebook server on a given port, and, back on your machine, starts an ssh-port-forwarding to the cluster to the given port. Your notebook then should appear on your default web browser on your local machine.
