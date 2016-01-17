## IFI/Genetics 2016 Self-Guided Tutorials


The purpose of Hackathon 2016 is to introduce bioinformatics/computational biology to Penn's IGG and GGR students who are not familiar with bioninformatics and computational biology. 

First year GGR students taking GCB535/Introduction to Bioinformatics are already familiar with these topics and 
are encouraged to participate. 

##### Problem definition

Hackathon is divided into two phases. In Phase I, you will be given two files called "a.bam" and "b.bam". 
One of these files relate to targets of a particular (but unknown to you) protein binding the genome (ChIP-seq) and the other is simply sequencing the input DNA (background). Your job is to identify which file corresponds to protein-DNA
binding and uncover the identity of this protein. Writing a shell script with two major command can answer the question:
	- peak calling
	- motif analysis
You can find more information about these steps in the following. We will fully explain the major steps required to solve this problem during a meeting on February 23, 2016. We will briefly described the phase II of Hackathon for more
advanced students. The following describes some basics to solve this problem. 

##### Topics to be covered:

  - Intro to Command-line
  - Intro to ChIP-seq analysis
  - Peak-calling software (MACS)
  - Genomic coordinates (bedtools)
  - Motif analysis (Homer)

### Intro to Command-line
Before computers had fancy pictures and shiny buttons, everything on a computer was done using text on a command-line. The command-line is simple, effective, and easy to learn. All software for analyzing NGS datasets are designed to be run through the command-line, and it's only a matter of time before you stumble across the command-line in your career.

Almost everything can be done on the command-line by just understanding about half a dozen topics:

 - Structures of directories and folders
 - Creating directories
 - Changing directories
 - Listing directories
 - Copying files
 - Wildcards

The excellent tutorial found [here](http://cli.learncodethehardway.org/book/) will teach you the basics of using the command line in about a day or two. Simple as that!

#### Intro to ChIP-seq
If a protein (such as a transcription factor) binds to DNA in the nucleus, ChIP-seq allows you to locate and quantify these interactions. This is a powerful research tool, allowing you to map protein-DNA interactions across the entire genome. The analysis is straight-foward, and will be a central focus of Hackathon 2016. These following Harvard edX course videos are a great introduction to ChIP-seq.

- Introduction to Transcriptional Regulation
    - https://youtu.be/yNtahPOVdEE
- ChIP-seq Technique
    - https://youtu.be/tn_SZElBDOA
- ChIP-seq Peak Calling
    - https://youtu.be/933kKxGdD90
- ChIP-seq Quality Control
    - https://youtu.be/nDrsyvntCw0

### Intro to Peak-calling software
Let's say you did a ChIP-seq experiment. The sequencing facility gives you a file containing millions of DNA sequences. Using this data, you need to distinguish the locations in the genome that had genuine protein-DNA interactions amongst all the "noise" (i.e., background DNA that was unintentionally sequenced). This process is called peak-calling, and one of the best programs for accomplishing this is called [MACS](http://liulab.dfci.harvard.edu/MACS/). The following video is a nice glimpse as to how MACS is used.

- Hands On Tutorial on Running MACS
    - https://youtu.be/r9zxzskkJ7Y

### Genomic coordinates (bedtools)
So now you run MACS and have the location of all the binding sites of your protein of interest. What is the most efficient way of reporting all these protein binding locations (which may be numbered in the tens of thousands)?  The answer is simple: a text file with each row corresponding to a binding location that is encoded by the chromosome number, the basepair number of the start position, and the basepair number of the end position. For example:

>chr14&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;14900&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;15000  
    chr14&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;167200&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;167400

In this example, these are the genomic coordinates of where your protein was found to be bound to the DNA. One interaction was at chromosome 14 that starts at position 14,900 and ends at position 15,000. The second interaction is also at chromosome 14 and starts at position 167,200 and ends at position 167,400.

These genomic coordinates are output into text files called BED and BEDGRAPH files. If generated using a Peak-calling program such as MACS, these files can also be referred to as peak files. Each row in these files correspond to a certain location of protein-DNA interaction, and there may be thousands of rows in a single file. These files may also have additional columns beyond the first three already listed. These extra columns can give you information such as the strand or the strength of the interaction.

##### Bedtools
Let's say you had two BED files (i.e., peak files). The first one listing all the binding sites of a transcription factor, and the second one listing all the locations of a certain histone modification. Each file has 10,000 rows. How would you find the overlapping regions between the two files? Only a crazy person would attempt this by hand! That is where the program [bedtools](http://bedtools.readthedocs.org/en/latest/) comes to the rescue. Bedtools has a variety of tools that allows you to answer questions such as this. For example, the bedtools function *intersect* would allow you to test for overlapping regions between these two bed files and output these results to a third file. 

#### Motif analysis (Homer)
Let's say you have a peak file of transcription factor binding sites generated using MACS that has 10,000 rows. How would you look for the DNA sequence that is recognized by this transcription factor? This is a job for [Homer](homer.salk.edu/homer/chipseq/peakMotifs.html). Homer takes a peak file and looks for short sequences of DNA that show up more often than expected, and returns the results as a sequence logo that looks like this:

![alt text](https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcSNypO0st8QWUNYn_vr2AvR7-OvJ6RM9vhz9mC539edhphx6-cc)

Homer also looks through multiple databases of previously characterized transcription factor binding sites, and returns the most likely match. In this example, Homer would tell you that this is likely a member of the GATA family of transcription factors.

#### Conclusion
The purpose here is to just introduce you to the basic concepts of some of the topics that will be covered at **IFI/Genetics 2016**. 
Hope to see you at the Hackathon!

If you have any questions, please contact us at <IFI.genomics.hackathon@gmail.com>

