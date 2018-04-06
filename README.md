# mtDNA-Server
This repository includes the new mtDNA-Server workflow starting with BAM files. The workflow can be executed locally without  transfering any data. 
For initial read mapping (FASTQ to BAM), we recommend using [bwa mem](https://github.com/lh3/bwa). 

The publicly available web service [mtDNA-Server](https://mtdna-server.uibk.ac.at) also includes read mapping. 

## Getting Started
 The workflow outputs homoplasmic and heteroplasmic sites using [Mutation-Server](https://github.com/seppinho/mutation-server), haplogroups using [HaploGrep](http://haplogrep.uibk.ac.at/) and contamination using [mitolib](https://github.com/haansi/mitolib). 
 
1) Install the workflow engine [Cloudgene](https://github.com/genepi/cloudgene)

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

   a. Command line Execution
   
   ```
   ./cloudgene run mtdna-server-1.1.1 --input apps/mtdna-server-1.1.1/*/test-data
   ```

   b. Graphical Execution
   
   ```
   ./cloudgene server
   ```
   To execute a job, open your web browser and enter http://localhost:8082. Use `admin` and `admin1978` to login.

## Workflow steps

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplogrep.uibk.ac.at
* Check Contamination with https://github.com/haansi/mitolib


