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

### vcf2bed

Sometimes I need to convert a VCF file to a BED format.

### vcf-tstv-stats

The script prints a table with the number of variants (SNV and indel)
and the ts/tv ratio. It works with multisample VCF too.

### insertSize

Calcute the BAM insert.
It uses **samtools** and the **pairend\_distro.py** from the **lumpy-sv** package.
I renamed the script to **pairend\_distro\_biolucxum.py** to avoid possible conflict
with the **lumpy-sv** package.


### genderPredictor

I wrote this utility to verify the gender in one or more BAM files.
The program uses the samtools idxstats to count the reads in
chromosome X and Y and print out some coverage statistics.

## License

Copyright 2018 [Luciano Xumerle](mailto:luciano.xumerle@gmail.com)

The programs are free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Please read the LICENSE file.
