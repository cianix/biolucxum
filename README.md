# biolucxum

Some bioinformatics tools to simplify my life


## Installation

To install in directory **/usr/local/bin**:

~~~
make install
~~~

## Programs description


### extract\_variants

I rewrite a perl version of this program from the [gvcftools](https://github.com/sequencing/gvcftools)


### get\_called\_regions

I rewrite a perl version of this program from the [gvcftools](https://github.com/sequencing/gvcftools)


### getVariantsSelected

The script filter out all the VCF lines without almost a valid variant gentype
(PASS and with a number grater than 0 in a GT field).


### sampleSelected

The script selects a subset of samples from the input VCF.
It uses a txt file to set one sample ID for line and the samples order.


### gvcf2evcf

The programs returns an eVCF file using a reference VCF to expand
reference regions in gVCF file.

A first release of this program is available at
https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0132180


### vcf2table

Parse the VCF file and create a table with CHR, POSITION, REFERENCE ALLELE, ALTERNATIVE ALLELE(s), GENOTYPE(s).


### vcf2bed

Sometimes I need to convert a VCF file to a BED format.


### vcf2AlleleBED

To convert a VCF file to a bed file with column: chr, start, stop, allele1, allele2.
Alleles are reported as **R** for the reference and as **A\>B** for alternative.


### vcf-tstv-stats

The script prints a table with the number of variants (SNV and indel), the heterozygosity ratio
and the ts/tv ratio. It works with multisample VCF too.


### typedSampleVCF

For each variant, the script prints out the number and the percentage of typed samples.


### catVCF

Concatenate several VCF to standard output.


### compareVCF

A simple script to compare the gentypes from a pair of VCF files.


### fullBundle2subset

To build a GATK reference genome with less chromosomes, all the unuseful chromosomes must be removed
from the fasta file and from all the VCF.gz files in the bundle.
*fullBundle2subset* takes in input the samtools faidx file of the new reference and and a vcf.gz and
print out a new VCF file without the unwanted contigs.


### prepareGenomeSizeXML

Used to prepare the "GenomeSize.xml" file needed by Illumina genomes.


### plinkHWE2avinput

The script prints out an avinput table importing a plink HWE table in
which the variant ID column is formatted as:

	CHR_STARTPOS_ENDPOS_REF_ALT

Example:

~~~~
 CHR                SNP     TEST   A1   A2        GENO   O(HET)   E(HET)       P
   1   chr1_10108_C_CCT      ALL  CCT    C       0/3/1     0.75   0.4688       1
   1   chr1_10108_C_CCT      AFF  CCT    C       0/2/1   0.6667   0.4444       1
   1   chr1_10108_C_CCT    UNAFF  CCT    C       0/1/0        1      0.5       1
   1    chr1_10114_T_TA      ALL   TA    T       0/4/3   0.5714   0.4082       1
   1    chr1_10114_T_TA      AFF   TA    T       0/0/1        0        0       1
   1    chr1_10114_T_TA    UNAFF   TA    T       0/4/2   0.6667   0.4444       1
   1   chr1_10145_AAC_A      ALL    A  AAC       0/1/7    0.125   0.1172       1
   1   chr1_10145_AAC_A      AFF    A  AAC       0/1/0        1      0.5       1
   1   chr1_10145_AAC_A    UNAFF    A  AAC       0/0/7        0        0       1
~~~~


### addUMI

The script reads *bwa* output from STDIN and add the RX tag to each reads.
It requires the gzipped fastq files for read1, read2 and UMI sequences and
the same reads order in all the fastq files.


### insertSize

Calcute the BAM mean insert size using a subset of reads.

It uses **samtools** and the **pairend\_distro.py** from the **lumpy-sv** package.
I renamed the script to **pairend\_distro\_biolucxum.py** to avoid possible conflict
with the **lumpy-sv** package.


### genderPredictor

I wrote this utility to verify the gender in one or more BAM files.
The program uses the samtools idxstats to count the reads in
chromosome X and Y and print out some coverage statistics.


### bedLength

The program prints out the length of a BED file.


### bedSlop

An alternative to the *bedtools slopbed*.
The script manages negative slop values too.
*There isn's a control on chromosomes lenght*.


### printPhreadTable

The program prints out the *Phred* or *Q score* values
for the range [0..42] corresponding to the range [33..75]
with the default *ASCII_BASE = 33*

NOTE: Old Illumina fastq uses *ASCII_BASE = 64*


### realPath

A perl replacement for the realpath(3) command.


### csv2wiki

The script loads a TSV file and prints out the dokuwiki table
and the markdown table.


### tex2pdf

It converts latex code to a PDF image using the programs: latex, dvips and epspdf


### xls-tsv

The program converts an Excel file to the TSV format
or a TSV file the XLSX format using file extension.

**NOTE**: This is a wrapper to the *ssconvert* program
      released with *gnumeric*.


## License

Copyright 2018 [Luciano Xumerle](mailto:luciano.xumerle@gmail.com)

The programs are free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Please read the LICENSE file.
