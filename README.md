# Mott Haven (Port Morris) apartments 

This repository contains data scraped and analyzed from various sources in relation to luxury apartments and new developments in the Port Morris / Mott Haven neighborhood in the South Bronx. 

Data scraping work is done in partial fulfillment of the requirements for the **Practical Python for News Investigations** class under [Sandeep Junnarkar](https://github.com/sandeepmj) at the Craig Newmark Graduate School of Journalism at CUNY. The resulting data will be used for a reporting assignment for the [Mott Haven Herald](https://motthavenherald.com/). 

Each branch in the repository corresponds to a data source. 

## Data sources

* [MNS Bronx real estate market report](https://www.mns.com/bronx_rental_market_report)
* [StreetEast buildings list in Mott Haven](https://streeteasy.com/buildings/mott-haven)


## Process

### Scraping
I mostly used `BeautifulSoup` to scrape webpages and `wget` and `os` to download files. 

In special circumstances, such as in scraping StreetEasy webpages, I used `async` `Playwright` to access content then fed it to `BeautifulSoup` for parsing. [(H/T to Jonathan Soma for this advice!)](https://jsoma.github.io/advanced-scraping-with-playwright/)