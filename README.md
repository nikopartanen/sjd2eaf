# Textfiles to ELAN processing instructions

To get started just write to Terminal:

    git clone https://github.com/nikopartanen/sjd2eaf

At first you have to install R or RStudio on your computer and run lines:

    install.packages("plyr")
    install.packages("dplyr")
    install.packages("XML")

This installs the packages required for the script to run. It has to be done only once. Whenever the script is executed it calls these packages through library() command.

You have to have the following folder structure:

    |-sjd-transform
      |-README.txt
      |-saxon9he.jar
      |-sjd-xml2eaf.xsl
      |-sjd2eaf.R
        |-eaf
        |-temp
        |-txt

Saxon XSLT and XQuery Processor Home Edition can be downloaded from [here](http://sourceforge.net/projects/saxon/files/Saxon-HE/9.6/). It has been published as open source so in principle it could be added here as well, but I need to check the exact licence first and see what has to be included with it.

Go in Terminal to the folder sjd-transform and write:

    Rscript sjd2eaf.R

This runs the script sjd2eaf.R. What should happen is that your **temp** folder gets filled with XML files and **eaf** folder gets filled with ELAN files. Now there is some bug that all ELAN files had the lenght of exactly five minutes that was certainly not the intention.

## Copyright

CC BY 4.0
Freiburg Research Group in Saami Studies / Niko Partanen 2014

## Contact

Please let us know if you have some improvements to this code!

nikotapiopartanen@gmail.com
