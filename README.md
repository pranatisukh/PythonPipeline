# PythonPipeline
#Project

## Dependencies:
To run this pipeline, you need to have the following tools and software installed:

- **Bowtie2**: For aligning sequencing reads to a reference genome.
- **SPAdes**: For genome assembly.
- **Samtools**: For manipulating SAM/BAM files.
- **BLAST**: For sequence similarity searching.

#These tools have to be installed and available in your system's PATH before running the pipeline.

## How to Run:

1. Clone this repository to your local machine: git clone https://github.com/pranatisukh/PythonPipeline.git
2. cd PythonPipieline
3. Make a directory to store files
    mkdir PipelineProject_Pranati_Sukh
    cd PipelineProject_Pranati_Sukh
4. Run Script: python PythonPipeline.py

Steps that will run: 
- FASTQ files will be retrieved from the SRA database
- HCMV genome reads will be mapped using Bowtie2.
- SPAdes will be used to filter mapped reads and perform genome assembly 
- Number of contigs with length > 1000 bp will be counted and the total assembly length will be calculated
- A BLAST search will be performed with the longest contig against the Betaherpesvirinae subfamily

Create sample data: 
1. prefetch SRR5660033  #get from NCBI
2. fastq-dump --split-files SRR5660033  #convert to Fastq file
3. head -n 40000 SRR5660033_1.fastq > sample_SRR5660033_1.fastq    #contains only first 10,000 reads
4. head -n 40000 SRR5660033_2.fastq > sample_SRR5660033_2.fastq    #contains only first 10,000 reads

Sample Test Data: python PythonPipeline.py --input sample_SRR5660033_1.fastq --output sample_output
