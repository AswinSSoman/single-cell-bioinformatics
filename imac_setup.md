# Instructions for setting up iMacs at CSHL

Author: Olga Botvinnik<br>
Email: olgabot@ucsd.edu<br>
Date: 2016-06-06<br>

This document sets up fresh iMacs with no bioinformatics tools to be ready for running alignments and counting reads.

- 1. Start downloading a gzip of all the data
```
curl https://s3-us-west-2.amazonaws.com/single-cell-bioinformatics/data.tar.gz > single-cell-bioinformatics-data.tar.gz
```
- 2. Open a new tab and download latest Miniconda for Python3 and save as `miniconda.sh`
```
curl https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -o miniconda.sh
```
- 2. Install Miniconda with defaults (`-b` flag) into specific folder
```
bash miniconda.sh -b -p $HOME/miniconda
```
- 3. Add `~/miniconda/bin` to `$PATH`
```
export PATH="$HOME/miniconda/bin:$PATH"
```
- 4. Add R and [Bioconda](https://bioconda.github.io) channels
```
conda config --add channels r
conda config --add channels bioconda
```
- 5. Install Bioinformatics packages
```
conda install --yes STAR samtools subread bedtools cutadapt
```
- 6. Make all the folders
```
mkdir -p ~/genomes/mm10/gencode/m8/ ~/projects/shalek2013/raw_data ~/projects/shalek2013/processed_data ~/projects/shalek2013/scripts
```
- 7. Unzip the data. This creates a folder called `single-cell-bioinformatics`
```
tar xzvf single-cell-bioinformatics-data.tar.gz
```
- 8. Move everything in the `single-cell-bioinformatics` folder down to the home folder
```
mv single-cell-bioinformatics/* ~/
```
