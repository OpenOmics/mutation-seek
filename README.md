<div align="center">
   
  <h1>mutation-seek 🔬</h1>
  
  **_An awesome quantitative genetics pipeline_**

  [![tests](https://github.com/OpenOmics/mutation-seek/workflows/tests/badge.svg)](https://github.com/OpenOmics/mutation-seek/actions/workflows/main.yaml) [![docs](https://github.com/OpenOmics/mutation-seek/workflows/docs/badge.svg)](https://github.com/OpenOmics/mutation-seek/actions/workflows/docs.yml) [![GitHub issues](https://img.shields.io/github/issues/OpenOmics/mutation-seek?color=brightgreen)](https://github.com/OpenOmics/mutation-seek/issues)  [![GitHub license](https://img.shields.io/github/license/OpenOmics/mutation-seek)](https://github.com/OpenOmics/mutation-seek/blob/main/LICENSE) 
  
  <i>
    This is the home of the pipeline, mutation-seek. Its long-term goals: to boldly detect physiological homogeneity within genetic heterogeneity and to perform error-prone data preparation for genome-wide association studies (GWAS) like no pipeline before!
  </i>
</div>

## Overview
Welcome to mutation-seek! Before getting started, we highly recommend reading through [mutation-seek's documentation](https://openomics.github.io/mutation-seek/).

The **`./mutation-seek`** pipeline is composed several inter-related sub commands to setup and run the pipeline across different systems. Each of the available sub commands perform different functions: 

 * [<code>mutation-seek <b>run</b></code>](https://openomics.github.io/mutation-seek/usage/run/): Run the mutation-seek pipeline with your input files.
 * [<code>mutation-seek <b>unlock</b></code>](https://openomics.github.io/mutation-seek/usage/unlock/): Unlocks a previous runs output directory.
 * [<code>mutation-seek <b>install</b></code>](https://openomics.github.io/mutation-seek/usage/install/): Download reference files locally.
 * [<code>mutation-seek <b>cache</b></code>](https://openomics.github.io/mutation-seek/usage/cache/): Cache remote resources locally, coming soon!

**mutation-seek** is an comprehensive pipeline for quantitative genetics. It relies on technologies like [Singularity<sup>1</sup>](https://singularity.lbl.gov/) to maintain the highest-level of reproducibility. The pipeline consists of a series of data processing and quality-control steps orchestrated by [Snakemake<sup>2</sup>](https://snakemake.readthedocs.io/en/stable/), a flexible and scalable workflow management system, to submit jobs to a cluster.

The pipeline is compatible with data generated from Illumina short-read sequencing technologies. As input, it accepts a set of FastQ files and can be run locally on a compute instance or on-premise using a cluster. A user can define the method or mode of execution. The pipeline can submit jobs to a cluster using a job scheduler like SLURM (more coming soon!). A hybrid approach ensures the pipeline is accessible to all users.

Before getting started, we highly recommend reading through the [usage](https://openomics.github.io/mutation-seek/usage/run/) section of each available sub command.

For more information about issues or trouble-shooting a problem, please checkout our [FAQ](https://openomics.github.io/mutation-seek/faq/questions/) prior to [opening an issue on Github](https://github.com/OpenOmics/mutation-seek/issues).

## Dependencies
**Requires:** `singularity>=3.5`  `snakemake>=6.0` `snakemake<8.0`

At the current moment, the pipeline uses a mixture of enviroment modules and docker images; however, this will be changing soon! In the very near future, the pipeline will only use docker images. With that being said, [snakemake](https://snakemake.readthedocs.io/en/stable/getting_started/installation.html) and [singularity](https://singularity.lbl.gov/all-releases) must be installed on the target system. Snakemake orchestrates the execution of each step in the pipeline. To guarantee the highest level of reproducibility, each step of the pipeline will rely on versioned images from [DockerHub](https://hub.docker.com/orgs/nciccbr/repositories). Snakemake uses singularity to pull these images onto the local filesystem prior to job execution, and as so, snakemake and singularity will be the only two dependencies in the future.

## Installation
Please clone this repository to your local filesystem using the following command:
```bash
# Clone Repository from Github
git clone https://github.com/OpenOmics/mutation-seek.git
# Change your working directory
cd mutation-seek/
# Add dependencies to $PATH
# Biowulf users should run
module load snakemake singularity
# Get usage information
./mutation-seek -h
```

## Contribute 
This site is a living document, created for and by members like you. mutation-seek is maintained by the members of OpenOmics and is improved by continous feedback! We encourage you to contribute new content and make improvements to existing content via pull request to our [GitHub repository](https://github.com/OpenOmics/mutation-seek).


## Cite

If you use this software, please cite it as below:  

<details>
  <summary><b><i>@BibText</i></b></summary>
 
```text
Citation coming soon!
```

</details>

<details>
  <summary><b><i>@APA</i></b></summary>

```text
Citation coming soon!
```

</details>

<!---
# Setup from mutation-seek template
```bash
# Add your new pipeline name here,
# whatever you set here will be the
# name of your cli too. Please make 
# sure it does not contain any spaces
# It should only contain, alpha-numeric
# characters and hyphens. 
new_pipeline_name="add_your_pipeline_name_here"

# Dry-run: This step automagically builds a 
# command to update any instances of the string
# mutation-seek with your new pipeline name, please
# make sure to set the variable above to whatever
# you want to name the pipeline and CLI.
find . -type f -not -path '*/.mutation-seek_version' -not -path '*./CHANGELOG.md' -not -path '*/.git/*' -exec grep 'mutation-seek' {} /dev/null \; | awk -F ':' '{print $1}' | sort | uniq | sed "s/^/sed -i 's@mutation-seek@$new_pipeline_name@g' /g"

# Updates any instances of the string mutation-seek
# with the name you decided/set above.
find . -type f -not -path '*/.mutation-seek_version' -not -path '*./CHANGELOG.md' -not -path '*/.git/*' -exec grep 'mutation-seek' {} /dev/null \; | awk -F ':' '{print $1}' | sort | uniq | sed "s/^/sed -i 's@mutation-seek@$new_pipeline_name@g' /g" | bash

# Rename the cli or main entry point 
# of the pipeline
mv mutation-seek "$new_pipeline_name"
```
-->


## References
<sup>**1.**  Kurtzer GM, Sochat V, Bauer MW (2017). Singularity: Scientific containers for mobility of compute. PLoS ONE 12(5): e0177459.</sup>  
<sup>**2.**  Koster, J. and S. Rahmann (2018). "Snakemake-a scalable bioinformatics workflow engine." Bioinformatics 34(20): 3600.</sup>  
