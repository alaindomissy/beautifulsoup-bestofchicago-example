Introduction to WebScraping and BeautifulSoup
=============================================

http://www.crummy.com/software/BeautifulSoup/bs4/doc/

What is it ?
------------
a Python library designed for quick turnaround of website-scraping projects

Why use it ?
------------
* facilitate data access : unleash valuable data that was once locked up in poorly-designed websites

* (semi-)automate /speed up data retrieval : repetitive  projects that would have taken hours take only minutes instead 

* caveat
  * you need to figure out at least once how to get hold of the wanted data
  * does not guess/ clever forage for you

How do you use it ?
-------------------

* give a URL to BeautifulSoup to parse

* will parse anything it gets from given URl and build a tree traversal

* then ready for you to ask BeautifulSoup questions like
  * "Find all the links", 
  * or "Find all the links of class externalLink", 
  * or "Find all the links whose urls match "foo.com", 
  * or "Find the table heading that's got bold text, then give me that text."

* outputs results ready for further processing: prettyprint, log, csv file, database...


Similarities ?
--------------

* Thoughts ?   jQuery and the DOM ?
* Comments ?
* Questions ?


3048 meters view of code
------------------------

```
# kitchen robot
def make_soup(given_url):
    html_page = urlopen(given_url).read()
    return BeautifulSoup(html_page, "html5lib")
 
# prepare a meal
my_soup = make_soup("http://www.messybutworthy.com/deep/andweird/bestof?key=sesameouvretoi&year=2010&cat=snakes")

# dig up the good stuff
list_of_interesting_items = my_soup('li', class_="bestOfItem" )

# collect the hidden gems
list_of_wanted_urls = [eachitem.a['href'] for eachitem in list_of_interesting_items ]
    
```


Three powerful features
-----------------------

* few simple methods and Pythonic idioms for navigating, searching, and modifying a parse tree
  * don't need much code around provided syntax to build an application

* automatically converts incoming documents to Unicode and outgoing documents to UTF-8 -  * no need to think about encodings

* sits on top of popular Python parsers like lxml and html5lib
  * different parsing strategies available with various tradeoff speed/flexibility
 
| Parser               | Install     | language  |  Speed   |Lenient           |
|----------------------|:------------|:----------|:---------|:-----------------|
| Python’s html.parser | included    | HTML      | decent   |lenient(py>2.7)   |
| lxml’s HTML parser   |ext C depend.| HTML      |very fast |lenient           |
| lxml’s HTML parser   |ext C depend.| XML(only1)|very fast |  NOT             |
| html5lib (pypi)      | pypi depend.| HTML      |very slow |extremely lenient |
 

html5lib behaves like a browser, and creates valid HTML5 


Need more power ? Beautiful vs Scrapy
-----------------------------------------------------

###Scrapy :  

* a complete framework for web-scraping / crawling / web-spider
* give Scrapy a root URL to start crawling, 
* specify constraints
  * how many number of Urls you want to crawl and fetch,
  * etc., 

###Beautiful Soup :  

* a single parsing library 
* fetches contents from given Url 
* easy syntax to parse certain parts fetched contents
* does not crawl : only fetches contents of given URL and stops

   
* Thoughts?  the Django of webscraping ? versus Jinja2 ?
* Comments ?
* Questions ?


Tutorials / Examples
---------------------------

###Alain's revised version in ipython notebook  (THE HARD WAY?)
https://github.com/alaindomissy/beautifulsoup-bestofchicago-example


### original inspiration : web-scraping-101-with-python (OUTDATED!)
http://www.gregreda.com/2013/03/03/web-scraping-101-with-python/#http://www.popsugar.com/Celebrities-Using-Instagram-21244293#opening-slide


###Trey's CLI for finding-drm-free-audiobooks (USEFUL!)
http://treyhunner.com/2014/05/cli-for-finding-drm-free-audiobooks/


Thanks !
--------
* Russia
* Chris
* Trey
* Melanie
* Saturday Pangea Workshop Crowd, SDPUG and PyLadies
* ... etc ...
