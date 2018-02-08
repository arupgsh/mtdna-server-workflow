# mtDNA Server Workflow
The new mtDNA-Server workflow from BAM to final variants. All executed locally. We also provide a web service to this: https://mtdna-server.uibk.ac.at/

Currently the following steps are included:

* Create homplasmies/heteroplasmies with https://github.com/seppinho/mutation-server
* Calculate haplogroups with http://haplogrep.uibk.ac.at/
* Check Contamination with https://github.com/haansi/mitolib

## Installation

Install Cloudgene with the following commands:

```
mkdir cloudgene
cd cloudgene
curl -s install.cloudgene.io | bash
```

Install mtdDNA Server Workflow:

```
./cloudgene gh seppinho/mtdna-server-workflow@latest
```

## Getting Started



```
./cloudgene server
```

Open your web browser and enter http://localhost:8082. Use `admin` and `admin1978` to login.

