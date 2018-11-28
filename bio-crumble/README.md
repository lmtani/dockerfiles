# Crumble

> source: https://github.com/jkbonfield/crumble

## Common execution

```
samtools view -H sample.bam > header.sam
samtools view -bh sample.bam \* > unplaced.bam
parallel --gnu "crumble -O BAM -r {} sample.bam output.{#}.bam" :::: contigs.txt
samtools cat -h header.sam -o sample_crumbled.bam $(ls output*.bam)
```
