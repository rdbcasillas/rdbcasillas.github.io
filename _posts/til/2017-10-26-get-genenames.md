---

layout: post
title: "TIL how to get Gene info from a list of chromsome coordinates of motifs"
categories: til

---

TIL how to get RefSeq's gene names from a set of chromosome coordinates. Suppose you have a file that contains DNA motifs (a place where a transcription factor binds). You want to know the genes inside which these motifs reside.  But unfortunately you only have *chromosome name*, *start* and *stop* positions for them. How do you find out the corresponding genes? 

There are multiple ways to do it. Numerous online tools allow you to paste the information you have and with a single click of a button, provide you with list of genes. These online tools aren't very helpful though if this step of getting gene names is part of your bigger Bioinformatics pipeline. USCS's database can be queried using command line and with some *awking* and *seding* you should be good.  But I was looking for a simpler solution in my favorite language Python. Enter [cruzdb](https://pypi.python.org/pypi/cruzdb). 

Following are the steps (for Mac OS X  and Ubuntu):

1. Grab the tarred copy of cruzdb from [here](https://pypi.python.org/pypi/cruzdb). Right click the link and use *wget* on command line to save it locally. 

2. Once downloaded, use the following command to unpack the stuff inside the compressed directory:

   ```shell
   tar -xvf cruzdb-0.5.6.tar.gz 
   ```

   This will create cruzdb directory. *cd* into it.

3. There will be a *setup.py* file inside that directory. Do: 

   ```shell
   sudo python setup.py install
   ```

    This will install the cruzdb package and make it importable from within   Python. 

4. Next, you need mysql & sqlalchemy as cruzdb depends on it. Simply do:

   ```shell
   pip install mysqlclient sqlalchemy
   ''' or use brew package manager for mysql (if on Mac):
   brew install mysql 

   '''For Ubuntu, you may have to install following too before the pip command: 
   sudo apt-get install libmysqlclient-dev
   ```

5.  Now start your favorite Python IDE. I prefer [Jupyter notebook](http://jupyter.org/) as it is  more interactive than others. Following is the Python script:

   ```python
   ## Import all the relevant libraries. If you have a 
   ## tab-delimited or csv file, I recommend Pandas as it 
   ## simplifies iteratiion over a file. 
   from cruzdb import Genome 
   import MySQLdb
   import pandas as pd

   # I was interested in Mouse but you can use any genome of interest
   genes_mm9 = Genome(db="mm9") 

   df_motiflist = pd.read_csv("/path/to/your/coordinate/csv")

   # Create a list that will store the results of a query that demands gene names based on 3 parameters
   geneObjects = []  
   for index, row in df_motiflist.iterrows():
       geneObjects.append(genes_mm9.bin_query('refGene', row['chromsome'],int(row['start']),int(row['stop'])))

   ## Above query results in an array of sqlalchemy Query
   ## objects. These objects can contain more than one 
   ## entries so we need to loop over it too
   myGenes = [] 
   for genes in geneObjects:
       for gene_name in genes:
           if gene_name.name2 not in myGenes: # only want unique gene names in the final list
               myGenes.append(gene_name.name2)
   ```

   *myGenes* list will contain all the genes that cruzdb could find. It's of course possible that some regions were in *enhancers* or *promoters* so there were no corresponding genes. 

   **Note**: I have only used the *"name2"* method of the sqlalchemy Query object to get the gene names but there are many methods availabe including the ones that provide you info on exons, introns, UTRs etc.  For a comprehensive list of methods, check cruzdb's documentation [here](http://pythonhosted.org/cruzdb/). 

If you further want to store this Python list of genes (and other info) into a file, convert the list into a Pandas dataframe and the write it out as a csv: 

```python
my_df = pd.DataFrame(myGenes)
my_df.to_csv("mygenelist.csv", index=False)
```

That's it! :D