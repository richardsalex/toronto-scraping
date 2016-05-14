# Scraping without coding

### Some current tools of the trade

Like many freebie software tools we enjoy using for journalism, these can come and go for various reasons (a good example of this is [Kimono](https://www.kimonolabs.com/)). These are best for simple scraping tasks.

-
Some links to use as a testing ground:

[NRC list of power reactor units](http://www.nrc.gov/reactors/operating/list-power-reactor-units.html)

[Chicago Police list of annual reports](http://home.chicagopolice.org/inside-the-cpd/statistical-reports/annual-reports/)

[FDA food recalls, withdrawals and safety alerts in 2015](http://www.fda.gov/Safety/Recalls/ArchiveRecalls/2015/default.htm?Page=1)


-

### [import.io](http://import.io)

import.io exists as both a web application and a standalone tool you can use from your computer desktop. What makes it unique compared to some of these other tools is that it has some built-in recognition for pagination schemes that may exist in an online data set.

Scraping with import.io comes in two flavors, presently:

- [magic](https://magic.import.io/examples): import.io automatically detects data and prepares it for download
- [extractor](http://support.import.io/knowledgebase/articles/407431-create-an-extractor): you pick and choose precisely what you want it to do

All "magic" needs is a URL to get started.

Creating an "extractor" or a "crawler" that can go through multiple pages requires the standalone application.

-

### [Web Scraper (Chrome extension)](http://webscraper.io/)

Create a sitemap for a page and pick off text, links and tables. Results can be strange — best to save this one for simple work that you can check.

-

### [Google Sheets](http://www.google.com/sheets)

They make it ridiculously easy to scrape tables whole and in part with a built-in function: `ImportHTML()`

```
=ImportHTML(table_url, type, element_number)
```

Where:

- **table_url** = the URL of the web page where the table is located.
- **type** = specify "table" or "list," which will target `<table>` and `<li>` tags, respectively.
- **element_number** = in the case of multiple tables or lists on one web page, specify which one you're after. Indexed to 0, so to grab the third table on the page, you would put a "2" here.

If I wanted to grab the entire table of reactors from [this page](http://www.nrc.gov/reactors/operating/list-power-reactor-units.html) on the Nuclear Regulatory Commission's site, I would input the following into a Google Sheets cell:

```
=ImportHTML("http://www.nrc.gov/reactors/operating/list-power-reactor-units.html", "table", 0)
```

This is a bit more complicated, but the function can also navigate what's known as an [XPath](http://www.w3schools.com/xsl/xpath_syntax.asp) to target a specific part of a table instead of the whole thing. HTML and XML are structured sort of like a tree, with content on different branches.

-

### [DownThemAll! (Firefox add-on)](http://www.downthemall.net/main/install-it/downthemall-101/)

This Firefox plugin has been around for a while; if you're faced with a web page that has a myriad of links with many documents or other content you need to collect, [DownThemAll!](https://addons.mozilla.org/en-US/firefox/addon/downthemall/) makes it relatively easy to target those links and retrieve the files.

For example, if I wanted to swiftly grab all the PDF files located on the Chicago Police Department's [crime statistics page](https://portal.chicagopolice.org/portal/page/portal/ClearPath/News/Crime%20Statistics), DownThemAll! can be set to acquire only PDFs that it finds.

-

### [Outwit Hub](http://www.outwit.com/)

[Outwit Hub](http://www.outwit.com/) exists as a standalone piece of software designed to harvest structured data from web pages. It also comes with a range of tutorials to get you started and understand its functionality.

The software can automatically detect tables and lists on web pages, but it can also use pattern matching to extract contents in more complex situations.

-




