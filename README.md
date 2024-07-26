The initial data preparation, genotyping and filtration were executed using STACKS v2.62 (https://catchenlab.life.illinois.edu/stacks/) and stacks workflow v2.62 (https://github.com/enormandeau/stacks_workflow) following the methods described by Rochette and Catchen (2017). The demultiplexed reads were aligned to the reference genome using the Burrows-Wheeler Aligner (BWA v0.7.17-r1188) with parameters -k 19 -c 500 -O 0,0 -E 2,2 -T 0 (Li H. and Durbin R., 2009). These were further processed with SAM tools v1.8 with the flags -Sb -q 1 -F 4 -F 256 -F 2048, which converted data into the binary format (BAM) while also filtering based on mapping quality and read types (Li et al., 2008). To conclude the procedure, the population module from STACKS was run with parameters -p 1 -r 0.5 --ordered-export --fasta-loci --vcf to execute the last step of the STACKS pipeline, calculating population genetics statistics, exporting data in various formats, and conducting genotyping. 
After genotyping, using STACKS steps, filtering of identified SNPs was performed using an in-house Python script, 05_filter_vcf_fast.py, with parameters 3, 60, 0 and 1 so that all genotypes had a minimum coverage of 3, and all samples combined had at most 40% missing SNP data. This filtering process facilitated the generation of a high-quality dataset suitable for downstream genetic analysis.
