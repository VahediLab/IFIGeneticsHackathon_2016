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
