
# 1. Installation locally

Please download the compressed R package here: [HAPS](https://github.com/Annie-Yanru-Cui/HAPS/blob/master/HAPS_0.1.0.tar.gz)

## 1.1 On Windows system

Make sure that your R is installed in 'c:\program files'

Install Rtools in 'c:\program files'

Add R and Rtools to the Path Variable on the Environment Variables panel, including

c:\program files\Rtools\bin

c:\program files\Rtools\gcc-4.6.3\bin

c:\program files\R\R.3.x.x\bin\i386

c:\program files\R\R.3.x.x\bin\x64

Run the following code in R

```R
install.packages('HAPS_0.1.0.tar.gz', repos = NULL, type='source')
```

## 1.2 On Linux and Mac systems

Just run the following code in R

```R
install.packages('HAPS_0.1.0.tar.gz', repos = NULL, type='source')
```

# 2. Basic example
There are three functions in ***HAPS***. 
* haplo.GWAS perform the GWAS using the haplotype data
```R
haplo.GWAS(Strfile=NULL,Manhattan=TRUE,Genefile=system.file("examples/genotype.sample.txt.gz", package="HAPS"),Phefile = system.file("examples/phenotype.sample.csv", package="HAPS"),Chrom ="all",max.merge=5,num.comp=3,p.adjust.method ="fdr",threshold=0.05)
```
* haplo.GS perform the genomic prediction using the haplotype data
```R
haplo.GS(Strfile=NULL,Genefile1=system.file("examples/training.geno.txt.gz",package="HAPS"),Phefile1=system.file("examples/training.phe.csv",package="HAPS"),Genefile2=system.file("examples/predict.geno.txt.gz", package="HAPS"),max.merge=3,num.comp=3)
```
* haplo.CV.GS perform the genomic prediction using the haplotype data through the cross validation
```R
haplo.CV.GS(Strfile=NULL,Genefile=system.file("examples/training.geno.txt.gz", package="HAPS"),Phefile = system.file("examples/training.phe.csv", package="HAPS"),Chrom ="all",max.merge=3,num.comp=3,nfold=10)
```
# 3. parameter setting
* **haplo.GWAS**

 **Strfile**: file name of the population structure.
             The first column of this file is the line, the other columns are the population structure data. If the file dose not exist, Strfile=**NULL**
	     
**Manhattan**: a logical value ( TRUE/FALSE) whether output manhattan plots

**Genefile**: the file name of genotype data 

**Phefile**: the file name of phenotype data

**Chrom**: represents chromsome number. 1 for the first chromsome; "all" for the whole chromsome

**max.merge**: a number greater than 2. When the number of haplotypes minus the max.merge,then these haplotypes are combined, **default is 5**. 
### This parameter setting depends on your population size, please adjusting the parameter to get the perform results

**num.comp**: a number indicating how many components were selected as the fixed effects,**default is 3**

**p.adjust.method**: method for adjust p value, **including "holm", "hochberg", "hommel", "bonferroni", "BH", "BY", "fdr", "none"**
 
**threshold** a threshold value for significant tests, **0.05/0.01/defind any number**
 
* **haplo.GWAS**


