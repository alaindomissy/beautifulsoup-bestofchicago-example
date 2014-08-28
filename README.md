beautifulsoup-bestofchicago-example
===================================

# Introduction

This workshop will be easier to follow if you have some familiarity with BeautifulSoup documentation or if you refer to it as you go: [http://beautiful-soup-4.readthedocs.org/en/latest]  

# Acknowledgment

This workshop is inspired from the following tutorial and Github Gist python script:  

* [http://www.gregreda.com/2013/03/03/web-scraping-101-with-python/#http://www.popsugar.com/Celebrities-Using-Instagram-21244293#opening-slide]  
* [https://gist.github.com/gjreda/f3e6875f869779ec03db]  

# Adaptations  

The following adaptations have been made : 

* we are using the html5lib library instead of the lxml librar. Being purely python with no requirement for cpython or libxml2 and libxslt c libraries, html5lib seems easier to install than lxml, and for the purpose of this workshop  did not seem to incur a prohibitive performance penalty  
* the target website used as an example has been modified since the original post was published.  
  * the first website page processed now has different DOM structure: the section of interest within which the urls are searched for can no longer be recognized as a dl tag with \"boccat\" class. Instead we will here directly identify all the links of interests by taking advantage of the fact they can be recognized as div tags with a 'BestOfItem' class  
  * the second tyoe of website pages processed also now has different DOM structure: the runners_up are no longer in a tag inside of the h2 tag. Instead we find them moving up to the parent of the h2 tag and looking at the first li tag within that  

# Setup instructions

see SETUP_INSTRUCTIONS.md

- full instructions are given if needed to setup Python, an interactive Interpreter, the BeautifulSoup and HTML parsing packages
- these setup instructions can be skipped if your setup is already done or if you prefer an alternative setup
- the example is here presented using an ipython notebook,
- the use of an virtualenv (with the wrapper) is also presented as away to install ipython and its dependencies, as well as the he BeautifulSoup and HTML parsing packages
- the previous two methods (ipython,virtualenv) are optional; you may prefer to use a traditional python interpreter ; you may prefer to install all your packages in your global environement 
- indications are given where to skip and jump if desired, so you can focus directly on the core subject of this website data scraping example