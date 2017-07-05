Description
-----------

MERLIN is a regulatory network inference algorithm that combines per-gene and per-module regulatory network inference methods. It infers both module memberships of genes, and regulators for individual genes and modules. It is based on a probabilistic graphical model.

**Options**

* d [required]: Text file with the expression data using the DREAM Challenge format (see File Formats)
* l: Text file with the list of regulators (see File Formats). Default: all genes are potential regulators.
* c: Text file that specifies the initial module assignments. Default: performs a random partitioning of genes into max [squareroot(n/2),30] clusters, where n is the number of genes in the data. That is the default option will have no more than 30 initial clusters.
* h: hierarchical clustering threshold (default 0.6)
* p: parameter for sparsity (default -5)
* r: parameter for module prior (default 4)
* k: max number of regulators that a gene can have (default 300)
* o [required]: name of output directory that must exist before running the program
* v [required]: number of folds for cross validation (default 1)

Notes
You don't need to set parameters that have default values or you can change the default value by setting different values. It is mandatory to set a value for options that don't have default (-data, -reg, -o).

Command-line usage
------------------

Merlin is a C++ tool, which can be downloaded from the repository and compiled on a linux machine.

**Command**
> ./merlin -d example/net1_expression.txt -c example/clusterassign.txt -o ./ -l example/net1_transcription_factors.tsv -v 1 -h 0.6 -k 300 -p 5 -r 4

Options are described above.

**Compilation**
To compile the code, type make in the source directory.

How to cite
-----------

> **Integrated Module and Gene-Specific Regulatory Inference Implicates Upstream Signaling Networks.**
> Sushmita Roy, Stephen Lagree, Zhonggang Hou, James A. Thomson, Ron Stewart, Audrey P. Gasch.
> PLoS Comput Biol, 2013.
> 
> http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003252

