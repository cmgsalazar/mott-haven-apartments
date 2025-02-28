# Mott Haven (Port Morris) apartments 

This repository contains data scraped and analyzed from various sources in relation to luxury apartments and new developments in the Mott Haven / Port Morris neighborhood in the South Bronx. 

Data scraping and PDF extraction work for the MNS real estate market reports were done in partial fulfillment of the requirements for the **Practical Python for News Investigations** class under [Sandeep Junnarkar](https://github.com/sandeepmj) at the Craig Newmark Graduate School of Journalism at CUNY. Notebooks and `csv` files labeled `regex` utilized the said library (instead of `re`) as part of the class requirements.

The resulting data analyses will be used for a reporting assignment for the [Mott Haven Herald](https://motthavenherald.com/). 

Each branch in the repository corresponds to a data source. 

## Project details

The data will drive a report on new real estate developments in the waterfront area of Mott Haven / Port Morris in the South Bronx. 

Specifically: the number of properties since 2019 in a specific area of the community; the number of complaints, violations, and litigations, if any; rental market trends (city-wide, borough-wide, and/or community-wide); and vacancy rates.

## Data sources

* [MNS Bronx real estate market report](https://www.mns.com/bronx_rental_market_report)
* [StreetEast buildings list in Mott Haven](https://streeteasy.com/buildings/mott-haven)
* [New York City Housing and Vacancy Survey](https://www.census.gov/programs-surveys/nychvs.html)
and [NYC Housing Preservation and Development](https://www.nyc.gov/site/hpd/about/research.page)
* [Displacement Alert Project (DAP) Portal](https://portal.displacementalert.org/)

## Content and process

I mostly used `BeautifulSoup` to scrape webpages and `wget` and `os` to download files. 

To extract text from PDFs, I used `pymupdf4llm`. 

### mns-rental-market

The `monthly-reports` and `yearend-reports` folders hold PDF files downloaded, while the `datasets` folder holds CSV files created by extracting text from the PDF files.

For files that use a different format or variables that returned `None`, I decided to manually fetch the data points I need and add them to the datasets.

There are two versions of notebooks and datasets for the MNS reports: one used `re` and the other used `regex` for regular expressions searches.

Regex was used to extract the following details: coverage period (month and/or year) and rental prices per report.

**Findings**: June 2019 consistently ranked as one of 10 months with the highest rental price across studio, one-bedroom, and two-bedroom apartments.

### streateasy-buildings

Listings were scraped from StreetEasy. There are two scraper versions: one utilized `async Playwright` — which I then fed to `BeautifulSoup` for parsing (H/T to [Jonathan Soma](https://jsoma.github.io/advanced-scraping-with-playwright/)  for this advice!) — and the other used `BeautifulSoup` and `headers`.

I then filtered data to show only buildings built in 2019 onward and within a particular area (with lat, lng coordinates).

**Findings**: Since 2021, average rental prices in Mott Haven have been higher than the borough’s average for all apartment types.