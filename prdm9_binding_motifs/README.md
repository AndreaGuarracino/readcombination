# PRDM9 binding motif search

We use the [`FIMO` (Find Individual Motif Occurrences)](https://meme-suite.org/meme/doc/fimo.html) tool from the MEME Suite to scan DNA sequences in FASTA format and identify individual instances where they match PRDM9 binding motifs. The position weight matrices (PWMs) representing these motifs were obtained from [Altemose et al., 2017](https://doi.org/10.7554%2FeLife.28383). You can find these matrices in the `PRDM9_motifs.human.txt` file.

Set your paths:

```shell
FIMO=/path/of/your/meme/installation/meme-5.5.5/src/fimo
PATH_FASTA=/path/of/your/sequences/assembly.fasta
DIR_OUTPUT=/path/of/your/output/folder/
```

Run `FIMO`:

```shell
$FIMO --oc $DIR_OUTPUT --verbosity 1 --thresh 1.0E-4 PRDM9_motifs.human.txt $PATH_FASTA
```

`FIMO` will generate several output files, including `fimo.tsv`, which contains the results in a tab-separated values (TSV) format.
