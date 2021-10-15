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
Python 3 >= 3.7  
biopython >= 1.76

`batch_merge.py` requires PANDAseq (https://github.com/neufeld/pandaseq)  
`mongoimport.py` requires MongoDB >= 2.6 (http://www.mongodb.org/) and pymongo >= 3.7

## Notes
You **don't** need to install *igblastn*. The binaries are included in this repository.  
*AbAnalysis* should work correctly with Windows(x86, x64), Linux, OS X

You can install almost all the requirements with *pip* or *anaconda*

pandaseq will require some level of professional skills to compile binaries for Windows.
OS X/Linux compiled versions you can find under the official releases tab on GitHub (https://github.com/neufeld/pandaseq/releases)