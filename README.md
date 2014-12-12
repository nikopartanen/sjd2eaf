# Textfiles to ELAN processing instructions

This is a script that converts simply formatted text files into ELAN XML files. It had few small demands for your file structure and also gives as output the ELAN structure used in Saami Research Group in Saami Studies. For different output the sjd-xml2eaf.xsl file has to be modified. This is relatively simple, just don't touch to the technical things. In principle there is nothing Kildin Saami specific in this script. However, as it runs correctly it's better to have it independent from other more experimental versions. This repository will be updated when some stable new features are added.

## Setup

To get started just write to Terminal:

    git clone https://github.com/nikopartanen/sjd2eaf

At first you have to install R on your computer and run these lines at Terminal (or in RStudio, or in R GUI, whatever you like):

    R
    install.packages("plyr")
    install.packages("dplyr")
    install.packages("XML")

This installs the packages required for the script to run. It has to be done only once. Whenever the script is executed it calls these packages through library() command.

You have to have the following folder structure:

    |-sjd2eaf
      |-README.txt
      |-saxon9he.jar
      |-sjd-xml2eaf.xsl
      |-sjd2eaf.R
        |-eaf
        |-temp
        |-txt

Saxon XSLT and XQuery Processor Home Edition can be downloaded from [here](http://sourceforge.net/projects/saxon/files/Saxon-HE/9.6/). It has been published as open source so in principle it could be added here as well, but I need to check the exact licence first and see what has to be included with it.

Your text files have to be formatted so that each line contains a sentence.

    This is a sentence.
    And so is this.
    Our number is irrelevant for this.

**NOT YET IMPLEMENTED**, but in principle easy to do, would be to have translations divided in similar fashion and being separated by tabs on the same row after each sentence.

Your file names should be formatted in a way that you want to have on your reference tier in the ELAN files. Usually this would correspond, as an example, to the session name. If you convert file called file.txt, then the content of reference tier will be:

    "file-1", "file-2", "file-3" and so on.

## Use

Go in Terminal to the folder **sjd2eaf** and write:

    Rscript sjd2eaf.R

This runs the script sjd2eaf.R. What should happen is that your **temp** folder gets filled with XML files and **eaf** folder gets filled with ELAN files. Now there is some bug that all ELAN files had the lenght of exactly five minutes that was certainly not the intention. Also my idea was that the folder **temp** would simply be deleted in the end of the script, but for now I've just left it there as it is.

## Copyright

CC BY 4.0
Freiburg Research Group in Saami Studies / Niko Partanen 2014

## Contact

Please let us know if you have some improvements to this code!

nikotapiopartanen@gmail.com
