---
layout: post
title: "TIL about tr command"
categories: til

---

Once you are introduced to small self-contained programs in Unix that do one thing well, the pleasure of creatively piping them to perform *file surgery* never ceases. In this TIL, I share a recent scenario that I dealt with to highlight this pleasure. 

Imagine you have a list of files that contain gene names in a particular column but some of those gene names happen to be in the same row. What I mean is this:

```
chr1	37956834	37957043|Lyg1
chr1	40790937	40791146|Mfsd9;Mfsd9
chr1	95375807	95376016|
chr1	121315462	121315671|Insig2;Insig2;Insig2;Insig2;Insig2
chr1	121970294	121970503|
chr1	121970312	121970521|
chr1	132233726	132233935|Lemd1;Lemd1;Lemd1;Lemd1;Lemd1;Lemd1
chr1	133424315	133424524|Sox13
chr1	186692087	186692296|Tgfb2;Tgfb2
chr1	189731906	189732115|Ptpn14;Ptpn14;Ptpn14
chr1	191965279	191965488|
chr10	8886252	8886461|Sash1;Sash1
chr10	12684207	12684416|Utrn;Utrn
chr10	22212552	22212761|H60b;Raet1a;Raet1c
chr10	45298649	45298858|Popdc3;Popdc3
chr10	61535129	61535338|Lrrc20
chr10	69452106	69452315|AK029407
chr10	75979710	75979919|Gm5134;Gm5134;Gm5134;Gm5134
chr10	77290910	77291119|Adarb1;Adarb1;Adarb1;Adarb1;Adarb1;Adarb1
chr10	79892887	79893096|Bc1;Prtn3;Prtn3;Elane;Cfd;Cfd;Med16;Med16;Med16
```

Notice the gene names after the "|" symbol. What if I wanted to capture all unique gene names in multiple files with hundreds of rows like this? Like this:

```
Lyg1
Mfsd9
Insig2
Lemd1
Sox13
Tgfb2
Ptpn14
Sash1
Utrn
H60b
Raet1a
Raet1c
```

Without Unix's default commands, process will be heavily manual with no pleasure. So, let's say I had *n* such files ***unstruct-1, unstruct2….unstruct-n*** and I want to store the unique gene names from them into ***genes-unstruct-1, genes-unstruct-2…genes-unstruct-2***. This is what I would do:

```shell
for f in ./unstruct*;
do (cut -d "|" -f2 $f | tr -s ";" "\n" | uniq > genes-${f});
done
```

That's it! Here's what happened:

1. A *for* loop was executed over all the files that start with a particular string. The '*' is for all files in a directory that start with a particular string. 
2. We start with the *cut* command and tell it to cut with "|" as the delimiter. This helps us use *-f2* because gene-list becomes the second column. If instead of "|", it was a tab character, we wouldn't have required *-d* argument and would have used -f4 (for 4th column). 
3. $f is our input file. Since we used "f" as the variable to represent a file in our *for* loop, we simply add a dollar sign in front of it to access that file.
4. The output from this first *cut* command goes into another command *tr* with the help from unix pipe. *tr* simply transforms your table. In this case, we wanted the genes in a single column instead of them being in straight line with ";" separating them. *tr* has a usefu lparameter *-s* that allows us to convert ";" into a new line character "\n". So while transforming, it moves the gene into the next line. 
5. Our final command *uniq* simply removes the duplicates from the gene list. 
6. And then we throw the output of this whole *pipeline* into a file that derives it's name from the original file. ${f} allows us to use the name of the original file as part of another string. We don't have to worry about naming our output files differently. 

It will depend on the size and the count of your original files but if you haven't played around with a combo of Unix commands before, you will be happily surprise with the speed.