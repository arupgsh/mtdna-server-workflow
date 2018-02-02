# mtDNA Server Workflow
The new mtDNA-Server workflow from BAM to final variants. All executed locally. We also provide a web service to this: https://mtdna-server.uibk.ac.at/

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplgrep.uibk.ac.at
* Check Contamination with https://github.com/haansi/mitolib
