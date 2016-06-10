# Hackathon 2016 Software Installation

Welcome to Hackathon 2016! We hope you had the chance to install the software you will be needing to complete today's challenges. If not, please visit the following websites and install these programs!

## [Homer](http://homer.salk.edu/homer/motif/)


### Basic installation instructions for Mac.

Install xcode by running this command in the terminal.
```bash
xcode-select –install
```
Install homebrew by running this command in the terminal
```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install wget by running this command in the terminal
```bash
brew install wget
```

Download Homer from the [link above.](http://homer.salk.edu/homer/download.html)
Move configureHomer.pl to where you want Homer install by using these commands (replace JJ with your computer's username).
```bash
mkdir /Users/JJ/Documents/Homer

cd /Users/JJ/Documents/Homer

wget http://homer.salk.edu/homer/configureHomer.pl
```

#### Install third-party software that is required for Homer.

Install ghostscript (to generate motif images) by running these commands.
```bash
wget https://github.com/ArtifexSoftware/ghostpdl-downloads/releases/download/gs919/ghostscript-9.19.tar.gz

tar zxvf ghostscript-9.19.tar.gz

cd ghostscript-9.19

./configure

make

sudo make install 
```

Install weblogo (to generate motif files) by running these commands (replace JJ with your username).

```bash
cd /Users/JJ/Documents/Homer

wget http://weblogo.berkeley.edu/release/weblogo.2.8.2.tar.gz 

tar zxvf weblogo.2.8.2.tar.gz
```

Install blat.

```bash
wget http://hgdownload.cse.ucsc.edu/admin/exe/macOSX.x86_64/blat/blat

chmod 755 blat
```

Install samtools.
```bash
wget http://downloads.sourceforge.net/project/samtools/samtools/1.3.1/samtools-1.3.1.tar.bz2

bunzip2 samtools-1.3.1.tar.bz2

tar xvf samtools-1.3.1.tar

cd samtools-1.3.1

make
```

Add the newly installed software to your path so your computer can find it (replace JJ with your username).

```bash
echo "PATH=$PATH:/Users/JJ/Documents/Homer/:/Users/JJ/Documents/Homer/weblogo:/Users/JJ/Documents/Homer/samtools-1.3.1" > ~/.bash_profile

source ~/.bash_profile
```

Run the installation command for Homer (replace JJ with your username).

```bash
cd /Users/JJ/Documents/Homer

perl /Users/JJ/Documents/Homer/configureHomer.pl -install

echo "PATH=$PATH:/Users/JJ/Documents/Homer/bin/" > ~/.bash_profile

source ~/.bash_profile
```

Install reference genome for mouse for Homer.

```bash
perl /Users/JJ/Documents/Homer/configureHomer.pl -install mm10
```

## [MACS 1.4](http://liulab.dfci.harvard.edu/MACS/)

### Basic installation instructions for Mac.


Install python
```bash
brew install python
```

Make a directory for your MACS installation (replace JJ with your username).

```bash
mkdir /Users/JJ/Documents/MACS1.4/

cd /Users/JJ/Documents/MACS1.4/
```

Download and install MACS
```bash
wget https://github.com/downloads/taoliu/MACS/MACS-1.4.2-1.tar.gz

tar zxvf MACS-1.4.2-1.tar.gz

cd MACS-1.4.2

python setup.py install
```

## [Bedtools](http://bedtools.readthedocs.io/en/latest/)

### Basic installation instructions for Mac.

Make a directory for Bedtools (replace JJ with your username).

```bash
mkdir /Users/JJ/Documents/Bedtools/

cd /Users/JJ/Documents/Bedtools/
```

Download and install bedtools.
```bash
wget https://github.com/arq5x/bedtools2/releases/download/v2.25.0/bedtools-2.25.0.tar.gz

tar -zxvf bedtools-2.25.0.tar.gz

cd bedtools2

make

```

Allow your computer to find your bedtools installation (replace JJ with your username).
```bash
echo "PATH=$PATH:/Users/JJ/Documents/Bedtools/bedtools2/bin" > ~/.bash_profile

source ~/.bash_profile
```

With the software installed, we can move onto the Hackathon challenge!
##

# Challenge #1

#### Your very talented collaborator has worked for months to optimize a ChIP-seq protocol and was successful! To celebrate, as well as recooperate, your collaborator has decided to take a sabbatical in a remote village in Indonesia to study tree frogs and will be without email or phone contact for the next six months. 

#### Not wanting to waste time you decide to move on with the sequencing and analysis. However, you soon come to realize that labels on the tubes have smeared and are illegible! You decide to submit the samples for sequencing under a generic label and hopefully sort the mess out later.

#### Fortunately, you do know the samples came from mouse and not human. Taking pity on you, a friend at the sequencing facility was kind enough to align the raw sequencing reads to the mouse reference genome, known as mm10, and provide you with the aligned .bam files. 

##### In a ChIP-seq experiment, DNA and protein are crosslinked together and sheared by sonication to generate short fragments of DNA attached to the proteins bound to the DNA. Using an antibody, your collaborator enriched for protein/DNA complexes through immunoprecipitation. As a control, your collaborator also collected DNA prior to the immunoprecipitation step (and is often called the Input control). The crosslinking is then reversed to separate the DNA fragments from the protein. The DNA fragments are then sequenced.



#### Now it's up to you to determine which sample was from the immunoprecipitated transcription factor, and which sample was from the Input control. Because of the anxiety of not knowing which tube was which you have also forgotten the transcription factor as well! (Maybe you need a vacation too). After determining which file is the IP, and which is the Input, you will also need to use your skills to determine the transcription factor for which your collaborator had originally IP'd.

#### As you do your analysis please keep track of your commands. After you have solved the challenge, please present your results to us. Good luck!

##
# Challenge #2

#### You have also performed ATAC-seq in the lymphoid lineage of immune cells. Although you have now determined the identity of your transcription factor, it is now up to you to determine from which cell type it came from. Your helpful friend has also aligned the raw sequencing reads to the mouse reference genome, mm10. The cells that you have sequenced include Hematopoetic stem cells (HSC), Multi-potent progenitors (MPP), Common lymphoid progenitors (CLP), CD8 T cells, CD4 T cells, Natural Killer (NK) cells, and B cells. 

##### In an ATAC-seq experiment, a transposase enzyme loaded with sequencing adapters is introduced into the nucleus of a cell. The enzyme will then insert the sequences into any region of the chromatin that is open and accessible to the enzyme. This process is called tagmentation, and the insertion of the sequences into the DNA also causes the DNA to be cut into fragments. These fragments, which now contain sequencing adaptors, can be sequenced and mapped back to the genome to tell you what genomic locations were accessible.

#### Once you have determined which cell type your ChIP-seq data was most likely derived from, please report your results to us. Good luck!
