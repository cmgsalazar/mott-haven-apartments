# Mott Haven (Port Morris) apartments 

This repository contains data scraped and analyzed from various sources in relation to luxury apartments and new developments in the Port Morris / Mott Haven neighborhood in the South Bronx. 

Some data scraping and PDF extraction work were done in partial fulfillment of the requirements for the **Practical Python for News Investigations** class under [Sandeep Junnarkar](https://github.com/sandeepmj) at the Craig Newmark Graduate School of Journalism at CUNY. Notebooks and `csv` files labeled `regex` utilized the said library instead of `re` as part of the class requirements.

The resulting data analyses will be used for a reporting assignment for the [Mott Haven Herald](https://motthavenherald.com/). 

Each branch in the repository corresponds to a data source. 

## Data sources

* [MNS Bronx real estate market report](https://www.mns.com/bronx_rental_market_report)
* [StreetEast buildings list in Mott Haven](https://streeteasy.com/buildings/mott-haven)

## Content

### mns-rental market

The `monthly-reports` and `yearend-reports` folders hold PDF files downloaded, while the `datasets` folder holds `csv` files created by extracting text from the PDF files.

For files that use a different format or variables that returned `None`, I decided to manually fetch the data points I need and add them to the datasets.

### streateasy-buildings

From the main list of buildings scraped from StreetEasy, I filtered data to show only buildings built in 2019 onward and within a particular area (with lat, lng coordinates).

## Process

I mostly used `BeautifulSoup` to scrape webpages and `wget` and `os` to download files. 

There are two scrapers for the StreetEasy webpages: one utilized `async Playwright` — which I then fed to `BeautifulSoup` for parsing [(H/T to Jonathan Soma for this advice!)](https://jsoma.github.io/advanced-scraping-with-playwright/) — and the other used `BeautifulSoup` and `headers`.

To extract text from PDFs, I used `pymupdf4llm`. There are two versions for the MNS reports: one used `re` and the other used `regex` for regular expressions searches.