#Tree visualization in R

##File formats: 
* `XXX` is single tree in [newick](http://en.wikipedia.org/wiki/Newick_format) format

* `PATH/TO/FILE` is path to the directory with your tree and data files

* `names.txt` is text file with two (tab separated) columns, with quotation marks surrounding text strings: 1) full taxon names, 2) taxon names in tree file
  
##Setting path and loading necessary libraries
```
setwd("PATH/TO/FILE")
library(ape)
library(phytools)
```

##Importing tree
`mltree<-read.tree("XXX")`

##Formatting tip labels: replacing short names from analysis with complete names for publication
```
names.dat<-read.table("names.txt",header=FALSE)
names<-data.frame(names.dat)
colnames(names)<-c("long","short")
mltree$tip.label<-names$long[match(mltree$tip.label,names$short)]
```

##Manipulating bootstrap support values

##Plotting tree

##Saving figure to file