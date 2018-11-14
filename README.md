# 6210_Assignment03
-------------------------------------------------------------------------------------------------------------------------------
User Documentation for Bioinformatics Programming 6410 Pipeline - README 
--------------------------------------------------------------------------------------------------------------------------------

1.Table of Contents 

1…………………..………………..………………..………………..………………...Table of Contents 
2........................................................ Name, version, description, and/or features of the program
3................................................................................................................... System requirements
4.......................................................... Install, uninstall, configuration, and operating instructions
5........................................................................................................................................ Files list
6......................................................Credit, acknowledgments, contact information, and copyright

2. Name, version, description, and program features 
(Each step number corresponds to the steps found in the comments of the pipeline script)

Our Targeted DNA-seq pipeline (v1.5) is an automated bioinformatics pipeline created using Bash programming language that reads a FASTQ file and uses an array of packages to create a VCF genotype table. This version of our pipeline is in progress as it takes features of the original Targeted DNA-seq pipeline (v1.0) and adds the options of using single-end or paired-end .FASTQ files (while the original only worked with single-end sequences). (1) In order for Sabre to demultiplex, some parameters need to be set to determine which path (i.e. single-end or paired-end) to take. FASTQ, barcode, reference genome file locations need to be specified. An additional step also requires Adapters for paired-end files to be specified. (2) A new working directory called “DeMulti” is created. This is the directory we will be working in. (3) Sabre is used to demultiplex (separate and categorise) barcoded reads into separate sequences from which they were derived from. There is an option for single-end and paired-end reads. (4) We then employ Cutadapt to remove the adapter sequences into the output log file and (5) align them using BWA. (6)-(9) The .SAM format is converted into .BAM using the samtools package and finally (10) we call for the variants using bcftools to generate the .VCF genotype likelihood table at each position.

3. System Requirements 

Software: 
Pipeline can be used in any unix-enabled computer OS including Windows, Linux, and Mac.

Pre-installed packages: 
For our pipeline script to run the following software tools must be installed
•	Sabre demultiplexing tool (obtained from https://github.com/najoshi/sabre)  
•	Cutadapt adapter sequence remover (https://github.com/marcelm/cutadapt)
•	Burrow-Wheeler Alignment (https://github.com/lh3/bwa)
•	Samtools, htslib, and bcf tools packages (https://github.com/samtools/samtools)




4. Install, uninstall, configuration, and operating instructions

Installation: 
No installation process is required, simply download our script form its Github repository to execute.

Running the script:  

Step 1 - Download from www.github/repository and save in your directory of choosing 

Step 2 - Give executive permission to run script

chmod +x /path/to/DNA-SeqV1.5.sh
Step 3 - Run script
/path/to/DNA-SeqV1.5.sh
./DNA-SeqV1.5.sh (if already in directory)

5. Files List

The files required to run the pipeline include:
•	FASTQ file(s) that is being converted into a VCF
•	Barcode file 
•	Reference genome

6. Credit, acknowledgments, contact information, and copyright

This script was written as part of a group assignment by Akaash, Nick, Paula, Phyllis, and Ruby using tools and commands learnt during our BINF*6410 (Bioinformatics Programming) class taught by Davoud Torkamaneh.
