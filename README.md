# transpipe
transpipe R-package for transcriptome pipeline




### Script used in the package

# import data

> data(exp)

> data(pheno)

# remove gene column and distinct row.names

> final<-filtermatrix(exp)

# filter for variable genes x=1 mean+1sd of variance

> variable<-varsig(final,x=1)

![variable](https://github.com/cdesterke/transpipe/blob/main/variable.png)

# pca
# palette examples : Set1, Set2, Set3, Pastel1, Pastel2, Dark1, Dark2, Accent

> pcatrans(variable,pheno,group="group",pal="Set1")

# limma DEG with control ref definition in phenotype

> res<-deg(variable,pheno$group,control="NT")

# volcanoplot

> vollimma(res,nb=500,fc=0.5,p=0.05,size=4,alpha=1)

# heatmap on significant genes

> bestheat(res,final,q=0.05,up=1,font=10)


abbreviations: 


