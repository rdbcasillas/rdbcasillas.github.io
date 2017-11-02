---

layout: post
title: "TIL little bit about AWS Lambda"
categories: til

---

Unix operating system has a [philosophy](https://en.wikipedia.org/wiki/Unix_philosophy) :

> Write programs that do one thing and do it well.

That's why when you begin to learn Unix command line tools, you realize that there are numerous small programs that do a great job at doing one specific thing. *grep* searches very well, *wc* is great at counting, *ls* is very powerful at simply listing directory content in different ways. Then you discover "pipes" which suddenly elevates the experience of using these small programs by combining them together and using the output of one program as an input for the other. Input goes in, output comes out, [Never a miscommunication](http://www.patheos.com/blogs/friendlyatheist/2011/03/25/tide-goes-in-tide-goes-out/)! 

What if this philosophy was applied to the world of cloud computing? Amazon Web Services (AWS) seems to be aspiring exactly for that, as over the last decade, they have introduced [gazillions of services](https://aws.amazon.com/) that promise do one specific thing and do it very well. At the root of it, the idea is to convince a develper or a company to do everything computational inside AWS. Using and managing servers, storing data, authenticating users, making database queries, machine learning, the list goes on and on. All of these different functionalities have their own "service" and these services can be connected to each other. The idea is to write less code outside of the core logic and presentation of your webapp. If you ever get overwhelmed by the insane list of AWS's badly named services (which you will), consider using [this script](https://gist.github.com/ideasasylum/2d7518611ffaacbc5061) that translates the service names into simple plain English. 

TIL little bit about [AWS Lambda](https://aws.amazon.com/documentation/lambda/). The purpose with this one is to allow the developers to only worry about writing small scripts (functions) that perform a particular task when triggered by an external event. Since I am a Bioinformatics person, I will use an example relevant to my field. 

Suppose you store your NGS reads in FASTQ files on S3 storage provided by AWS. Everytime a new FASTQ file is uploaded to your storage, you want to trigger a function that aligns the reads in that file to a reference genome. This triggering event can be done without Lambda, but the cool thing with Lambda is that it frees you from worrying about scaling your program with respect to increasing input. If someone uploads hundreds of fastq files at the same time, Lambda can automatically increase the resources required for your program to manage these files. And unlike AWS EC2, you are billed only based on number of requests made to the program that aligns the reads. This flexibility reduces the cognitive load associated with thinking about server configuration and saves money you may be draining by only using EC2 instances. Amazon likes to call the use of Lambda as "going serverless" but as Lynn Langit puts it in [this talk](https://www.youtube.com/watch?v=PgZ2dxnj734), it is more approriate to call Lambdas "Containerless". They are "**functions** that abstract away containers/ servers and are billed on **executions** , not server instance sizes."

After alignment, you can create numerous small Lambda funtions for post-processing of BAM files, calling variants, annotating variants etc. All these Lambda functions would be triggered based on external event. So you could even have a BAM file from an external source and use only your variant calling Lambda function without having to use alignment and post processing Lambdas. This clear separation of responsibilties among multiple *microservices* can give you more control over your Bioinformatics workflow compared to the traditional "end to end" pipelines. 

I am just beginning to learn AWS lambda. While I create something concrete, I will add future TILs specific to a particular goal achieved using AWS lambda. 

