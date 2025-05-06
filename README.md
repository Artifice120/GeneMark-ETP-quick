
Install dependencies with ```conda``` or  ```mamba```

```
micromamba create -n gmet-env -c bioconda -c conda-forge bedtools diamond gffread hisat2 sra-tools samtools stringtie perl-yaml-libyaml
micromamba activate gmet-env
cd $( which bedtools | awk -F '/bin/bedtools' '{ print $1 }' )
micromamba deactivate
```

Then clone the git-repo here:

```
git clone  https://github.com/gatech-genemark/GeneMark-ETP
mv GeneMark-ETP/tools ./
cp -r GeneMark-ETP/bin/* bin/
sed -i 's|CheckForVerison( "./|CheckForVerison( "|g' bin/check_ETP_tools.pl
```
Then activate the environemnt and test the installation

```
micromamba activate gmet-env
check_ETP_tools.pl
```


# GeneMark-ETP

Gene finding in eukaryotic genomes by GeneMark-ETP  

## Reference

_GeneMark-ETP: Automatic Gene Finding in Eukaryotic Genomes in Consistence with Extrinsic Data_  
Tomas Bruna, Alexandre Lomsadze, Mark Borodovsky <br>
[Genome Res. 2024. 34: 757-768](https://genome.cshlp.org/content/34/5/757.full)

Georgia Institute of Technology, Atlanta, Georgia, USA  

## Experiments

The repository with documentation of experiments, data, and results for the GeneMark-ETP project is available at https://github.com/gatech-genemark/GeneMark-ETP-exp  

## Instructions

Usage:
```
gmetp.pl --cores 32 --cfg input.cfg
```
Examples of input configuration files can be found at https://github.com/gatech-genemark/GeneMark-ETP-exp 

## Software license

### GeneMark-ETP pipeline

GeneMark-ETP is distributed under Creative Commons Attribution NonCommercial ShareAlike 4.0 License.
See the [full text of the license](License-Creative-Commons-Attribution-NonCommercial-ShareAlike-4.0-International.txt).  

### Third-party tools

Third-party tools are in the folder "tools." These tools are distributed under the licensing terms of the respective license holders. For details, see the installation instructions and corresponding references.

