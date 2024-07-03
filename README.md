# Web Scraping

Web scraping projects in Python, from my first BeautifulSoup scripts to a Selenium bot and a quotes scraper with a guessing game (2023-2024).

| Folder | Library | What it does |
|---|---|---|
| [beautifulsoup/](beautifulsoup) | requests, BeautifulSoup | Small scrapers for news, job, shopping and ranking pages. |
| [selenium/](selenium) | Selenium | A bot that searches Booking.com and reports the best deals, plus Selenium exercises. |
| [quotes-scraper/](quotes-scraper) | requests, BeautifulSoup | Scrapes every quote from quotes.toscrape.com into a CSV file, then turns it into a guessing game. |

## beautifulsoup

| Script | Scrapes |
|---|---|
| `main.py` | The BBC News RSS feed: title, description and publication date of each story, saved to `bbc_web_scraping.csv`. |
| `IMDb_movies_scraping.py` | IMDb's top TV shows chart. |
| `ebay_page_scraping.py` | Titles, prices and links of eBay search results. |
| `division_scraper.py` | A results table from a Division 2 ranking site. |
| `JimShapedCoding1.py` | Course cards from a local HTML page (`home.html`). |
| `JimShapedCoding2.py` | Python job offers from TimesJobs: company, skills and posting date. |
| `instagram_profile_scraping.py` | A first try at an Instagram profile page. |

Sample of `bbc_web_scraping.csv`:

| title | description | pubdate |
|---|---|---|
| Watch how the world brought in 2023 | As the world turns more and more countries greet 2023. | Sun, 01 Jan 2023 02:33:15 GMT |
| Archbishop of Canterbury calls for leaders to fix social care | The Most Reverend Justin Welby uses his new year's message to highlight the social care crisis. | Sun, 01 Jan 2023 00:05:48 GMT |

## selenium

- `bot/`: opens Booking.com, searches a destination with dates and a number of adults, keeps 3- to 5-star hotels and prints the deals found. The entry point is `bot/run.py`; it needs ChromeDriver, whose path is set in `bot/booking/booking.py`.
- `freeCodeCamp/`: first Selenium exercises (waiting for elements, sending keys, CSS selectors).

## quotes-scraper

- `csv_scraper.py` follows the pagination of [quotes.toscrape.com](https://quotes.toscrape.com/) and saves each quote, its author and the link to the author's page to `quotes.csv`.
- `csv_quote_game.py` picks a random quote from `quotes.csv` and gives you four guesses to find the author, with hints such as the author's birth date and place.
- `quotes_scraper.py` is the first version, which scrapes the quotes and plays the game in one go.

Sample of `quotes.csv`:

| text | author |
|---|---|
| “The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.” | Albert Einstein |
| “It is our choices, Harry, that show what we truly are, far more than our abilities.” | J.K. Rowling |

## Run it

```bash
pip install requests beautifulsoup4 pandas selenium
cd quotes-scraper
python csv_quote_game.py
```

Run each script from its own folder, since the scripts read and write files next to them.
