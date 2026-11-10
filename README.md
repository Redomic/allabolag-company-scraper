# Allabolag Scraper: Swedish Company Data & Financials

For prospecting, enrichment and monitoring: find Swedish companies and get flat rows with organisation number, SNI industry, employees, financials from the latest annual report (kSEK), equity ratio, and management/board role titles. Run by keyword, organisation number or URL, watch a list for new and changed companies, or follow the **newly registered companies feed** by industry and county for scheduled CRM/prospecting alerts.

**Run it in the cloud, no setup:** [https://apify.com/redomic/allabolag-company-scraper](https://apify.com/redomic/allabolag-company-scraper). Works on Apify's free plan; about $3.00 per 1,000 results
(less on paid plans). Schedules, API, webhooks and CSV/Excel/JSON export are built in.

## What you get
- B2B prospecting and lead enrichment in Sweden (firmographics + financial size)
- Account qualification (revenue, profit, headcount, industry, location)
- Change monitoring on a schedule (new, changed or removed companies)
- Newly formed company alerts by industry/county (SDRs, investors, accountants)

## Sample output
Real rows from a recent run: [`sample.json`](sample.json) · [`sample.csv`](sample.csv)

```json
{
  "orgNumber": "5560743089",
  "name": "Volvo Personvagnar Aktiebolag",
  "address": "Karossvägen 2",
  "municipality": "Göteborg",
  "county": "Västra Götaland",
  "industry": "10001228 Bilar",
  "sniCode": "10001228",
  "sniName": "Bilar",
  "latitude": 57.72335174,
  "longitude": 11.84670026,
  "employees": 20190,
  "revenueKSEK": 244217000,
  "profitKSEK": -7276000,
  "accountsScope": "legal_entity",
  "url": "https://www.allabolag.se/5560743089",
  "_source": "search",
  "equityRatio": 29.4,
  "fTaxRegistered": true,
  "fTaxDescription": "Ja, registrerad för F-skatt",
  "vatRegistered": true,
  "payrollTaxRegistered": true,
  "shareCapitalKSEK": 724889,
  "legalForm": "Aktiebolag",
  "companyFormCode": "Aktiebolag",
  "status": "ACTIVE",
  "registeredDate": "1960-10-28",
  "ceo": "Verkställande direktör",
  "boardTitles": [
    "Ordförande",
    "Ledamot",
    "Ledamot",
    "Ledamot"
  ],
  "fiscalYear": "2025",
  "fetchedAt": "2026-11-10T08:10:09.560740Z"
}
```

## Run it from code
Python ([apify-client](https://pypi.org/project/apify-client/)):

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("redomic/allabolag-company-scraper").call(run_input={"query": "volvo"})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

curl (waits for the run and returns the rows):

```bash
curl -X POST "https://api.apify.com/v2/acts/redomic~allabolag-company-scraper/run-sync-get-dataset-items?token=$APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"query": "volvo"}'
```

## All inputs, modes and pricing
See the full documentation on the Apify page: [https://apify.com/redomic/allabolag-company-scraper](https://apify.com/redomic/allabolag-company-scraper)
