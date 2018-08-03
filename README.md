# Web crawler

## Business Use Case


Your task is to write a simple web crawler in a language of your choice.
The crawler should:

- be limited to one domain. Given a starting URL – say wiprodigital.com 
- it should visit all pages within the domain, but not follow the links to external sites such as Google or Twitter.

The output should be a simple site map, showing links to other pages under the same domain, links to static content such as images, and to external URLs.
We would like to see what you can produce in a couple of hours – please don’t spend much more than that. In addition, please

- ensure that what you do implement is production quality code
- briefly describe any tradeoffs you make through comments and / or in a README file
- include the steps needed to build and run your solution
   
Once done, please make your solution available on Github and forward the link with brief instruction on how to run it

## Description

This project is using **crawler4j** internally to crawl pages.

Main tradeoffs:

- crawler4j requires temp directory to store data. 
- It has limit set to 500 pages. It can be changed by setting --max-pages param
- No support for www sub-domains it will treat it as external url
- it is not build as one jar because I had some problems with signed dependent jars

## Setup
    git $ clone https://github.com/A557252/webcrawlerPOC
    $ cd webcrawler-java/
    $ mvn clean compile
	$ mvn package

## Usage

Run:

    $ java -jar target/web-crawler-1.0-SNAPSHOT.jar

Mandatory parameter:

    -u,--url <arg>           website url
    
Optional parameters:

    -c,--crawlers <arg>      number of crawlers (1 by default)
    -d,--delay <arg>         delay in ms (200 by default)
    -m,--max-pages <arg>     max pages to fetch
    -o,--output-file <arg>   output file by default sitemap.xml
    -t,--temp-dir <arg>      temporary directory
    
    
Example:

    $ java -jar target/web-crawler-1.0-SNAPSHOT.jar --url="http://www.prudential.co.uk"
