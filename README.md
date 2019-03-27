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

### vcf2table

Parse the VCF file and create a table with CHR, POSITION, REFERENCE ALLELE, ALTERNATIVE ALLELE(s), GENOTYPE(s).

### vcf2bed

Sometimes I need to convert a VCF file to a BED format.

### vcf2AlleleBED

To convert a VCF file to a bed file with column: chr, start, stop, allele1, allele2.
Alleles are reported as **R** for the reference and as **A\>B** for alternative.

### vcf-tstv-stats

The script prints a table with the number of variants (SNV and indel)
and the ts/tv ratio. It works with multisample VCF too.

### insertSize

Calcute the BAM mean insert size using a subset of reads.

It uses **samtools** and the **pairend\_distro.py** from the **lumpy-sv** package.
I renamed the script to **pairend\_distro\_biolucxum.py** to avoid possible conflict
with the **lumpy-sv** package.


### genderPredictor

I wrote this utility to verify the gender in one or more BAM files.
The program uses the samtools idxstats to count the reads in
chromosome X and Y and print out some coverage statistics.


### bedSlop

An alternative to the bedtools slopbed.
The script manages negative slop values too.
*There isn's a control on chromosomes lenght*.


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
