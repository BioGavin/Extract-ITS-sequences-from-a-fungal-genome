# Extract-ITS-sequences-from-a-fungal-genome

ITSx (Bengtsson‐Palme *et al.*, 2013) is still the reference method to extract ITS sequences from genomic fasta files. It is however really slow.
More recently, Barrnap - a fast and accurate method to identify the location of ribosomal RNA genes - was developed.

By combining these two softwares and performing sequences comparison, this script allows the fast extraction of ITS sequences from fungal genomes.

```
python extractITS.py -which ITS2 -i genome.fasta -o ./output/ -name mySpecies
```

## Dependencies

- Python 3.x
- Barrnap: https://github.com/tseemann/barrnap
- ITSx: https://microbiology.se/software/itsx
- Biopython
- Pandas



# Installation tutorial from wlab

```bash
conda create -n ex_rrna python=3.8
conda activate ex_rrna
pip install biopython==1.72 pandas
conda install barrnap itsx
# download the script
git clone https://github.com/fantin-mesny/Extract-ITS-sequences-from-a-fungal-genome.git
cd Extract-ITS-sequences-from-a-fungal-genome
# run help
python extractITS.py -h
```



## Usage Example

### Run

```bash
mkdir output
python extractITS.py -which ITS2 --cpu 24 -i genome.fasta -o ./output/ -name mySpecies
```



### Output

```bash
# The output dereplicated ITS sequences are written in output/mySpecies.ITS2_filtered.fasta
$ cat output/mySpecies.ITS2_filtered.fasta
>mySpecies_#1 1 copies of this sequence found in genome.fasta
CAACCCTCAAGCACAGCTTGTGTGTTGAGCCTTCGTCCCCCCGTGGACGTGCCCGAAATG
CAGCGACGGCGTCGTGTTCCGGTGCCCGAGCATATGGGGCTTTGTCACCCGCTCTAGAGG
CCCGGCCGGCTCCGGCCCCATCTCAAACCCTTCGAGGGAGGACGGTCTTCGGGCCGGTCT
CCTCACCA
>mySpecies_#2 6 copies of this sequence found in genome.fasta
CAACCCTCAAGCGCGGCTTGTGTGTTGGGCCTTCGTCCCCCCGTGGACGTGCCCGAAATG
CAGCGGCGGCGTCGTGTTCCGGTGCCCGAGCGTATGGGGCTTTGTCACCCGCTCTAGAGG
CCCGGCCGGCTCCGGCCCCATCTCAAACCCTTCGAGGGAGGGCGGTCTTCGGGCCGGTCT
CCCCACCA
```

