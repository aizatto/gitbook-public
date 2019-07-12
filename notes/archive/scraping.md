# Scraping

Limitations:

* How many requests can their server take
* How long does it take for the server to handle a request
* Request/second
* How many requests can you parallelize
* From a single process
* From multiple process
* How do you track what needs to be scraped

Goals:

* Maximize number of requests/sec
* Less compute resources used

Tools:

* Database
* Queue

Database:

* Avoid nosql
* Use a SQL database from the start, since you’ll most likely be exporting/querying it
* Easier to change field names
* Run SQL queries to fix
* One table per “type” of page
* One table for the pagination results
* Another table for page results
* Another table for consolidated results
* This can be the source of truth
* Hard part may be figuring out what should exist in the consolidated table, but doesn’t

Log to the console:

* page/id scraped
* time scraped
* Time it took to scrape page

