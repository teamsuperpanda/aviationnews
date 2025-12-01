# Aviation News

## Description

This repository aggregates various aviation news sources and combines them daily into a JSON file (`news.json`). The resulting JSON data is utilized by our aviation-related applications: Pocket 737 and Falcon.

## Disclaimer

The applications Pocket 737 and Falcon display article titles, publication dates, and brief content snippets from the aggregated news. Full article content is not displayed within the apps to respect copyright laws. Users can click on article cards to open the original source websites for complete articles. This project is **not affiliated with, endorsed by, or sponsored by any of the news sources listed**. It is an independent aggregation of publicly available RSS data for informational purposes.


## Usage

Anyone is allowed to use the aggregated news data in `news.json` for their own projects, provided they comply with the copyright notices and disclaimers outlined above.

The news is collected from the following RSS feeds:

- **FlightRadar24**: https://www.flightradar24.com/blog/feed/
- **Avgeekery**: https://avgeekery.com/feed/
- **Australian Aviation**: https://australianaviation.com.au/feed/
- **Sam Chui**: https://samchui.com/feed/
- **The Aviationist**: https://theaviationist.com/feed/
- **Boeing (737 category)**: https://boeing.mediaroom.com/news-releases-statements?pagetemplate=rss&category=787
- **UK Aviation News**: https://ukaviation.news/feed/
- **Aviation Source News**: https://aviationsourcenews.com/feed/

## Automation

The aggregation process is automated using an n8n workflow that runs daily at midnight. The workflow:

1. Fetches RSS feeds from all sources.
2. Extracts relevant fields: title, pubDate, contentSnippet, link, and assigns a source name.
3. Merges all articles into a single stream.
4. Removes duplicate articles based on title.
5. Sorts articles by publication date in descending order (newest first).
6. Aggregates all data into a JSON array.
7. Commits the updated `news.json` file to this repository.

Each article in `news.json` includes:
- `title`: The article title
- `pubDate`: Publication date
- `contentSnippet`: A brief summary or snippet
- `link`: URL to the full article
- `source`: The name of the news source

## Copyright and Ownership
All copyrights, trademarks, and intellectual property remain the property of their respective owners.  
This project does **not** claim ownership of any third-party content and does **not** modify or republish copyrighted material.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
