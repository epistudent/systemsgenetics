
Authors: Raúl Aguirre-Gamboa and Niek de Klein

## Introduction 
Decon-eQTL is part of Decon2, a statistical framework for estimating cell counts using molecular profiling such as expression or methylation data from heterogeneous samples 
[(Decon-cell)](https://github.com/molgenis/systemsgenetics/tree/master/Decon2/DeconCell) and consecutive deconvolution of expression quantitative trait loci (Decon-eQTL) into each cell subpopulation.


## Requirements
`Java version 1.8 or higher` (Tested using `1.8.0_121`)  
Decon-eQTL-v*.*.*.jar

## Download

The latest .jar build can be downloaded from www.molgenis.org/jenkins/job/systemsgenetics/Decon-eQTL$Decon-eQTL/lastBuild/. Use Decon-eQTL-v*.*.*-jar-with-dependencies.jar.

### For compiling
commons-cli v1.3.1  
commons-csv v1.2  
commons-io v2.4  
commons-lang3 v3.4  
commons-math3 v3.6  
jsci-core  
jsci-mathmlimpl  
jsci-sci

## minimal usage example
    
    java -jar deconvolution -c <file containing cellcounts> \
                            -e <file containing expression data> \
                            -g <file containing genotypes>  \
                            -o <output directory> \
                            -sn <file with SNP and gene combination to test>
    
For a full guide see [Decon2 manual](https://github.com/molgenis/systemsgenetics/tree/master/Decon2)

## Options overview

    -c,--cellcount <file>                     Cellcount file name
    -e,--expression <file>                    Expression file name
    -g,--genotype <file>                      Genotype file name
    -gc,--genotypeConfigurationType <arg>     Which genotype configuration type to use (either all or two)
    -help                                     print this message
    -no,--no_console                          Do not output logging info to the console
    -o,--outfolder <path>                     Path to folder to write output to
    -oe,--outputPredictedExpression           Write output file with predicted expression
    -of,--outfile <file>                      Outfile name of deconvolution results (will be written in outfolder)
    -r,--round_dosage                         Round the dosage to the closest int
    -sn,--snpsToTest <file>                   Tab delimited file with first column gene name, second column SNP name. Need to match with names from genotype and expression files.
    -t,--test_run                             Only run deconvolution for 100 QTLs for quick test run
    -w,--whole_blood_qtl                      Add whole blood eQTL (pearson correlation genotypes and expression)
