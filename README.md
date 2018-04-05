# mtDNA-Server Workflow
This repository includes the new mtDNA-Server workflow starting with BAM files. Note: For mapping the reads (FASTQ to BAM) of the circular mitchondrial genome, we recommend using [bwa mem](https://github.com/lh3/bwa). 

Two tools exist:
- [Variant Detection Only](#variant-detection-only)
- [Complete mtDNA-Server Workflow](#run-mtdna-server-workflow)

## Complete mtDNA-Server Workflow
 The workflow outputs homoplasmic and heteroplasmic sites, haplogroups using [HaploGrep](http://haplogrep.uibk.ac.at/) and creates a contamination report. 
 
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

   a. Command line Execution
   
   ```
   ./cloudgene run mtdna-server-1.1.1 --input apps/mtdna-server-1.1.1/*/test-data
   ```

   b. Graphical Execution
   
   ```
   ./cloudgene server
   ```
To execute a job, open your web browser and enter http://localhost:8082. Use `admin` and `admin1978` to login.

## Variant Detection Only

if you don't want to execute the complete workflow and only interested in the variants, run the following tool:

### Download Tool
```
mkdir mutation-server
wget https://github.com/seppinho/mtdna-server-workflow/releases/download/1.1.1/mutation-server-1.1.1.jar -O mutation-server/mutation-server-1.1.1.jar
```
### Download Test Data

```
mkdir mutation-server/input-files
wget https://mtdna-server.uibk.ac.at/static/bam/rCRS.fasta -O mutation-server/input-files/rCRS.fasta
wget https://mtdna-server.uibk.ac.at/static/bam/HG00096.mapped.ILLUMINA.bwa.GBR.low_coverage.20101123.bam  -O mutation-server/input-files/HG00096.mapped.ILLUMINA.bwa.GBR.low_coverage.20101123.bam
```
### Run Tool
```
cd mutation-server
java -jar mutation-server-1.1.1.jar  analyse-local --input input-files  --reference input-files/rCRS.fasta --level 0.01 --outputRaw raw.txt --outputVar var.txt --baq true --baseQ 20 --mapQ 20 --alignQ 30 --indel true
```
The --indel feature only checks for deletions. 

## Workflow steps

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplogrep.uibk.ac.at
* Check Contamination with https://github.com/haansi/mitolib


