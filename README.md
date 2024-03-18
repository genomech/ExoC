# ExoC
  Effective molecular diagnosis of congenital diseases hinges on comprehensive genomic analysis, traditionally reliant on various methodologies specific to each variant type—whole exome or genome sequencing for single nucleotide variants (SNVs), array CGH for copy-number variants (CNVs), and microscopy for structural variants (SVs). We introduce a novel, integrative approach combining exome sequencing with chromosome conformation capture, termed Exo-C. This method enables the concurrent identification of SNVs in clinically relevant genes and SVs across the genome and allows analysis of heterozygous and mosaic carriers. 

  Here we developed several pipelines for searching chromosomal rearrangements as inversions and translocations in Exo-C data. You can find detailed instructions for these tools in corresponding folders.

  Each pipeline starts with .mcool file. We suggest creating a file with resolutions suitable for both pipelines. "ExoC-translocation-finder" pipeline uses resolutions: 1 kb, 16 kb, 256 kb, 4096 kb. "Inversion_search" pipeline uses resolutions: 10 kb, 100 kb, 250 kb, 1000 Kb. You can create .cool file using 1 kb resolution and then execute a `cooler zoomify` command with appropriate resolutions:
  ```
cooler cload pairs -c1 1 -p1 2 -c2 3 -p2 4 /path_to_hg19.chromsizes:1000 - sample_name_1Kb.cool
cooler zoomify  -r 1000,10000,16000,100000,250000,256000,1000000,4096000 -o sample_name.mcool sample_name_1Kb.cool
```
