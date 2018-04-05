# mtDNA Server Workflow
This repository includes the new mtDNA-Server workflow starting with BAM files. It outputs homoplasmic and heteroplasmic sites, haplogroups using [HaploGrep](http://haplogrep.uibk.ac.at/) and creates a contamination report. 

## Run mtDNA-Server workflow

1) Install the workflow engine [Cloudgene](https://github.com/genepi/cloudgene).

```
mkdir cloudgene
cd cloudgene
curl -s install.cloudgene.io | bash
```

2) Install the mtDNA Server workflow

```
./cloudgene gh seppinho/mtdna-server-workflow@1.1.1 -name mtdna-server-1.1.1
```
3) Run the workflow 

* Command line Execution
```
./cloudgene run mtdna-server-1.1.1 --input <bam-folder>
```

* Graphical Execution
```
./cloudgene server
```
Now, open your web browser and enter http://localhost:8082. Use `admin` and `admin1978` to login.

## Workflow steps

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplogrep.uibk.ac.at
* Check Contamination with https://github.com/haansi/mitolib
