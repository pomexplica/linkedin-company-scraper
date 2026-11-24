# LinkedIn Company Scraper (No Cookies): Posts, Similar Companies

Get any public LinkedIn company page as clean data: name, followers, employees on LinkedIn, industry, company size, type, headquarters, website, founded year, specialties, all office locations, **similar companies and the latest posts in the same result**, with no second Actor to run. Paste company URLs or just the slugs.

**[Run it on Apify](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)**: no install, no login, free credit on a new Apify account.

## What you get

- **Company profile**: name, description, logo, website, industry, company size range, company type, founded year, specialties
- **Numbers**: LinkedIn followers and employees on LinkedIn (exact counts)
- **Where they are**: headquarters plus every office address listed on the page, and the structured main address (street, city, region, postal code, country)
- **Similar companies** that LinkedIn shows next to the page (great for building lead lists by snowball)
- **Recent posts** (optional): text, date, likes and link
- **Clear status per company**: `ok`, `not_found`, `invalid_url` or `blocked`

## Pricing

**No login, no cookies, no LinkedIn account at risk. You pay only for companies delivered: $0.003 per company.** Pages that don't exist and invalid inputs are listed with the reason and never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~linkedin-company-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"companies": ["https://www.linkedin.com/company/google/", "apify"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/linkedin-company-scraper").call(run_input={"companies": ["https://www.linkedin.com/company/google/", "apify"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add linkedin-company "https://mcp.apify.com?tools=pomlabs/linkedin-company-scraper" -t http
```

## Ready-made examples

- [Get LinkedIn company data without cookies](https://apify.com/pomlabs/linkedin-company-scraper/examples/linkedin-company-data-without-cookies)
- [Latest posts of a LinkedIn company page](https://apify.com/pomlabs/linkedin-company-scraper/examples/linkedin-company-latest-posts)
- [Find similar companies on LinkedIn](https://apify.com/pomlabs/linkedin-company-scraper/examples/similar-companies-on-linkedin)

## More Actors by Pom Labs

- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper)

Full documentation, input fields and output format: [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies on Apify](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-company-scraper).
