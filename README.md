````markdown
# Book Scraper with Scrapy and MongoDB

This project is a web scraper built using the **Scrapy** framework to extract book data from [http://books.toscrape.com](http://books.toscrape.com), a website designed for practicing scraping techniques. The scraped data is stored directly in a **MongoDB** database.

## Features

- Extracts details of all books listed on the site.
- Automatically traverses pagination to scrape all available pages.
- Stores structured data into a MongoDB collection.
- Designed with a modular Scrapy spider and pipeline.

## Scraped Fields

Each book entry includes:

- **Title**
- **Price**
- **Availability**
- **Rating**
- **Product URL**

## Requirements

- Python 3.6+
- Scrapy
- pymongo
- MongoDB (running locally or accessible remotely)

## Installation

Install the dependencies:

```bash
pip install scrapy pymongo
````

Ensure MongoDB is installed and running:

```bash
sudo systemctl start mongodb
```

## Usage

Run the spider using Scrapy:

```bash
scrapy crawl books
```

This will scrape all pages and store book entries into your local MongoDB instance under:

* **Database**: `bookstore`
* **Collection**: `books`

## Project Structure

```
book_scraper/
├── book_scraper/
│   ├── __init__.py
│   ├── items.py          # Defines the data model
│   ├── pipelines.py      # MongoDB pipeline logic
│   ├── settings.py       # Scrapy settings
│   └── spiders/
│       └── books.py      # Spider definition
├── scrapy.cfg
```

## Configuration Notes

Ensure MongoDB settings (host, port, DB name, collection) are correctly set in `settings.py` or handled via environment variables in `pipelines.py`.

## License

MIT License

## Disclaimer

For educational and practice purposes only. The target site is open for scraping tests.
