# Wiley Scraper

![banner](https://i.ibb.co/DPBR1gXt/wiley-cover.png)

👋 Welcome to the Wiley Scraper! This actor extracts book and publication data from Wiley.com. With this actor, you can easily gather data about academic books, textbooks, research publications, authors, pricing, and more from this leading academic publisher.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-cNaH3xMdIMu0OkVGc-7FLYz4nTR6-id4sH5ijfc_1758526673236.jpeg" alt="Wiley.com Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/wiley-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


## Introduction

## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.2.1` |
| **Last Update** | Nov 30, 2025 |

---



The Wiley Scraper is a web scraping tool that extracts publication data from wiley.com. It is useful for academic research, bibliometrics, competitive analysis, and anyone interested in analyzing academic publications and textbooks.

## Use Cases

- **Academic Research**: Collect book metadata, authors, and publication details for literature reviews.
- **Bibliometrics**: Analyze academic publications, authors, and publishing trends.
- **Dataset Building**: Aggregate book metadata (ISBN, pages, publish dates) for research databases.
- **Price Monitoring**: Track pricing and availability of academic textbooks and publications.

## Input 📥

To use this actor, provide the following input fields:

- **startUrls** (array, optional): Direct URLs to scrape. Can include search pages or book detail pages.
- **query** (string, optional): Search term or keyword for books and publications.
- **maxItems** (integer, required): Maximum number of books to extract. Example: `50`
- **page** (integer, optional): Starting page number. Default: `1`
- **sortBy** (string, optional): Sort order for results. Options: `relevance`, `authorAtoZ`, `titleAtoZ`, `publishedNewToOld`, `publishedOldToNew`, `priceLowToHigh`, `priceHighToLow`
- **proxyConfiguration** (object, optional): Apify proxy configuration. Default: `{ "useApifyProxy": true }`

Note:

- You must provide at least one of `startUrls` or `query`.

Example input:

```json
{
  "query": "machine learning",
  "maxItems": 50,
  "sortBy": "relevance",
  "page": 1,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

## Output 📤

The output is a dataset of book objects with the following fields:

```json
{
  "title": "Charmed Knits: Projects for Fans of Harry Potter",
  "url": "https://www.wiley.com/en-ie/Charmed+Knits%3A+Projects+for+Fans+of+Harry+Potter-p-9780470067314",
  "authors": ["Alison Hansel"],
  "authorUrls": [
    "https://www.wiley.com/en-ie/search?filters[author]=Alison%20Hansel&pq=++"
  ],
  "productOptions": [
    {
      "type": "Paperback",
      "price": ""
    }
  ],
  "isbn": "978-0-470-06731-4",
  "image": "https://media.wiley.com/product_data/coverImage300/14/04700673/0470067314.jpg",
  "numberOfPages": "176",
  "publishDate": "May 2007",
  "description": "<b>Sit and Knit a Spell</b>   <p>You'll soon be knitting enchanting things you didn't know were  within your powers. Charmed Knits offers dozens of patterns for  items that evoke the mystique of Harry Potter - a Wizard Robe, an  Invisibility Shawl, a Quidditch Sweater, Ron's Ragg Raglan, a Clock  Blanket, Harry Christmas Ornaments, and more. Easy-to-follow  patterns, color photos of the finished projects, and illustrations  of special stitch patterns and design elements make it easy for all  knitters - from beginners to those at Mrs. Weasley's level&#160;-  to work knitting magic. Charmed Knits whisks you away on a  wonderful journey. Along the way, you can pick patterns inspired by  the Weasleys, stock up at Diagon Alley, show your house colors,  conjure up gifts, or create pieces to help you feel at home in the  magical world of Harry Potter.</p>",
  "aboutTheAuthor": "Alison Hansel is an avid Harry Potter fan and a popular knitting blogger whose daily missives can be read on the blue blog at alison.knitsmiths.us. The online go-to gal for Harry Potter tribute knitting, she has published patterns in the popular online knitting magazines MagKnits and Knitty.",
  "permission": "",
  "tableOfContents": ""
}
```

## How many books can the Wiley Scraper extract?

The scraper paginates through book listings and will extract up to the number specified in `maxItems`. If you want all available books, set a high value for `maxItems`.

## Why use the Wiley Scraper?

- ⚡️ **Fast**: Quickly gather academic book data for your needs.
- 🤙 **Easy to use**: No coding required—just input your search criteria and run.
- ☑️ **Well-Maintained**: Maintained by the Lexis Solutions team for reliability and updates.
- 🎯 **Flexible**: Support for multiple input methods (URLs, search queries, sorting options).
- 🔍 **Comprehensive**: Extracts detailed metadata including authors, pricing, and table of contents.

## FAQ 💬

- **Can I use this scraper to download full texts?**
  - No, this scraper extracts metadata and page-visible information only.

- **What if the website changes?**
  - If Wiley changes its website structure, the scraper may need to be updated. Please report issues or request updates as needed.

## Need to scrape other academic or publishing data sources?

Explore related actors on Apify:

- [Barnes & Noble Scraper](https://apify.com/lexis-solutions/barnesandnoble-scraper) - Books and publications
- [Companies House UK Scraper](https://apify.com/lexis-solutions/companies-house-uk-scraper) - UK company registry data
- [Kununu](https://apify.com/lexis-solutions/kununu-scraper) - Employer reviews (labor market research)
- [Jobs.ch](https://apify.com/lexis-solutions/jobs-ch-scraper) - Swiss job listings
- [InfoJobs](https://apify.com/lexis-solutions/infojobs-net-scraper) - Job listings
- [JobsDB](https://apify.com/lexis-solutions/jobsdb) - Asia job listings
- [Jobs.cz](https://apify.com/lexis-solutions/jobs-cz-scraper) - Czech job listings

---

👀 Need help or want a custom solution?

Lexis Solutions is a certified Apify Partner. We can help you with custom data extraction projects.

Contact us via [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)
