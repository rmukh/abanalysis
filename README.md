# AbAnalysis (updated)

## Usage

To run AbAnalysis on a single FASTA or FASTQ file:  
`python ab_analysis.py -i <input-file> -o <output-directory> -t <temp-directory>`

To iteratively run AbAnalysis on all files in an input directory:  
`python ab_analysis.py -i <input-directory> -o <output-directory> -t <temp-directory>`

## Additional options  
`-m, --merge` Input directory should contain paired FASTQ (or gzipped FASTQ) files. Paired files will be merged with PANDAseq prior to processing with AbAnalysis.
  
`-u N, --uaid N` Sequences contain a unique antibody ID (uaid) of length N. The uaid will be parsed and added to the JSON output.  
  
`-s, --species` Select the species from which the input sequences are derived. Supported options are 'human', 'mouse', and 'macaque'. Default is 'human'.  
   
`-n, --next_seq` Use if the sequences were generated on a NextSeq sequencer. Multiple lane files from the same sample will be merged.  
  
## Helper scripts  
Two helper scripts are included:  
`batch_merge.py` performs PANDAseq merging on a directory of paired FASTQ (or gzipped FASTQ) files.   
`mongoimport.py` iteratively imports a directory of JSON files into a MongoDB database.  
  
## Requirements  
Python >= 2.7
biopython < 1.76

batch_merge requires PANDAseq (https://github.com/neufeld/pandaseq)  
mongoimport requries MongoDB (http://www.mongodb.org/) and pymongo  

## Notes
You don't need to install *igblastn*. The binaries are included in this repository. 

*ab_analysis.py* should work correctly with Windows(x86, x64), Linux, OS X

biopython < 1.76 since it was the last version with Python 2.7 support