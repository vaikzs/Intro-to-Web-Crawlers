# Intro-to-Web-Crawlers
Web Information Systems 7900

## Size of Index Directory:
Its 4.9Mb.

![Number of vertices vs Time (ms)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/IndexSize.png)


## Introduction to Nutch 
The Nutch crawler will crawl the URL(s) that are present in the seed.txt file one per line. We will be editing the regex-urlfilter.xml just to say that we get the input URLs from the seed.txt in the particular regex format. We can also crawl the whole World Wide Web which might take ages to finish. My goal is to crawl a specific domain (www.knoesis.org). 

## Nutch data consists of:
Crawl_db, Link DB, Segments, crawl_generates, crawl_fetch, content, parse_text, parse_data, crawl_parse. 
## Bootstrapping from the seed list 
Here, the injector adds URL s to the crawl db. 
## The Fetch List - Segments
The pages that are yet to be fetched are stored as segments under crawl/segments folder from the crawl db. The segments are given TIMESTAMP. 
## 1000 Top Pages
Now for the new segment(s) that are generated we fetch the 1000 pages that have top scores. 
This is done twice. 
## Links - Inverted
The anchor text which are the hyper links in the domain are linked to corresponding pages, these are inverted and then indexed.
## Indexing – SOLR LUCENE
SOLR uses lucene api to index. The links and pages are indexed by solr. Before this setup Nutch is integrated with Solr, instructions are specified in the material. Now, the documents are indexes of the links anchor texts. This is exactly how the inverted index works. 


## The Crawl Script 

![The Crawl Script)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/CrawlScript.png)




The Nutch development team has provided a crawling script that does all the work that was given step by step above for the number of rounds specified as command line arguments with the script. 
  
## SOLR INTERFACE 
Querying limited to 10, returned 488. 
![SolrInterface)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/SolrInterface.png)
![SolrInterface2)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/SolrInterface2.png)




## FULL INTERFACE: 
Query starts from 3 to 7.
![FullSolrInterface1)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/FullSolrInterface.png)
![FullSolrInterface2)](https://github.com/vaikzs/Intro-to-Web-Crawlers/blob/master/Screenshots/FullSolrInterface2.png)

## References 
1. https://wiki.apache.org/nutch/NutchTutorial
2. http://lucene.apache.org/solr/




