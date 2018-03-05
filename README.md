# mtDNA Server Workflow
This repository includes the new mtDNA-Server workflow from BAM files to homoplasmies/heteroplasmies. All steps are executed locally. 

## Run mtDNA-Server workflow locally

1) Install Cloudgene with the following commands

```
mkdir cloudgene
cd cloudgene
curl -s install.cloudgene.io | bash
```

2) Install the mtDNA Server workflow

```
./cloudgene gh seppinho/mtdna-server-workflow@latest
```

3) Start the local web service
```
./cloudgene server
```

4) Open your web browser and enter http://localhost:8082. Use `admin` and `admin1978` to login.

## Workflow steps

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplogrep.uibk.ac.at/
* Check Contamination with https://github.com/haansi/mitolib
