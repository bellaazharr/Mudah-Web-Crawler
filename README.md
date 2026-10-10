# 🔎 Mudah.my Web Crawler

**A Python crawler that collects structured listings from Mudah.my, Malaysia's largest classifieds site.**

Built for SECP3133 High Performance Data Processing at UTM, as a team of four. I led the group and built the crawlers for the **Vehicles** and **Property** categories.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)
![asyncio](https://img.shields.io/badge/asyncio-concurrency-555?style=flat-square)
![Dask](https://img.shields.io/badge/Dask-parallel-FC6E6B?style=flat-square)

## The interesting part

My first versions used **BeautifulSoup** and then **Selenium** to parse the rendered pages. Both kept breaking, because the live site's HTML is complex and changes often.

The fix wasn't better parsing. I found that Mudah.my's search is powered by an **internal API**, so I called it directly. That was simpler, much faster and far more stable: it returns clean structured data, with no rendering and no fragile selectors.

The lesson I took away: "high performance" isn't only about optimising code. It starts with picking the right way to get the data in the first place.

## What it collects
**Target:** 100,000 listings

| Field | Example |
|---|---|
| Listing title | Honda City 1.5 V 2021 |
| Item type | Car / Apartment |
| Price | RM 78,000 |
| Region | Selangor |
| Seller | private or dealer |

## Stack
- **Collection:** Python, Requests, the Mudah.my internal API (with BeautifulSoup and Selenium as early attempts)
- **Speed:** asyncio for concurrent requests, multiprocessing and Dask for parallel cleaning
- **Environment:** Google Colab and Google Drive

## Team
| Member | Role |
|---|---|
| Ain Nurnabila | Group leader · Vehicles & Property crawlers · report intro & system design |
| Dayang | Crawler part B & data storage |
| Farra | Data cleaning & optimisation |
| Safiya | Optimisation & performance benchmarking |

---
<sub>SECP3133 High Performance Data Processing · Universiti Teknologi Malaysia</sub>
