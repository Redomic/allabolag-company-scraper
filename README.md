# Allabolag Scraper: Swedish Company Data & Financials

Get Swedish companies from allabolag.se as a spreadsheet: organisation number, industry (SNI code), address, employees, revenue, profit, equity ratio, growth, CEO and board roles, and the tax and VAT registration status. Search by name or keyword, list every company in an industry and region, or follow the companies registered in Sweden this week.

**Run it in the cloud, no setup:** [https://apify.com/redomic/allabolag-company-scraper](https://apify.com/redomic/allabolag-company-scraper). Works on Apify's free plan; about $0.40 per 1,000 results
(less on paid plans). Schedules, API, webhooks and CSV/Excel/JSON export are built in.

## What you get
Every company registered under SNI 62.10 (software development), sorted by revenue, on 15 November 2026:

| Company | Org number | City | Employees | Revenue (MSEK) | Profit (MSEK) | Equity ratio |
|---|---|---|---|---|---|---|
| Ericsson AB | 5560566258 | Stockholm | 13,052 | 134,244 | 19,602 | 49.6% |
| IFS World Operations AB | 5560406042 | Linköping | 553 | 7,448 | 1,022 | 45.5% |
| Tata Consultancy Services Sverige AB | 5565594008 | Stockholm | 211 | 5,567 | 405 | 60.5% |
| Embark Studios AB | 5591723019 | Stockholm | 318 | 3,821 | 364 | 17.9% |
| SAP Svenska AB | 5563229680 | Stockholm | 215 | 3,699 | 108 | 29.9% |
| Nasdaq Technology AB | 5563148138 | Stockholm | 993 | 2,656 | 365 | 77.1% |
| Consid AB | 5565994307 | Jönköping | 1,114 | 2,595 | 41 | 23.6% |

Each row also carries the legal form, registration date, status, full address, county, SNI code and name, a company description, estimated turnover, turnover year, gazelle and mortgage flags, revenue and profit growth, share capital, F-tax, VAT and payroll registration, payment remarks, parent company, the CEO and chair, and the last few years of accounts. The figures come in kSEK, as allabolag shows them.

## Sample output
Real rows from a recent run: [`sample.json`](sample.json) · [`sample.csv`](sample.csv)

```json
{
  "orgNumber": "5560743089",
  "name": "Volvo Personvagnar Aktiebolag",
  "marketingProtection": false,
  "address": "Karossvägen 2",
  "postalCode": "405 31",
  "postPlace": "Göteborg",
  "municipality": "Göteborg",
  "county": "Västra Götaland",
  "industry": "29101 Tillverkning av personbilar och andra lätta motorfordon",
  "sniCode": "29101",
  "sniName": "Tillverkning av personbilar och andra lätta motorfordon",
  "latitude": 57.72335174,
  "longitude": 11.84670026,
  "employees": 20190,
  "revenueKSEK": 244217000,
  "profitKSEK": -7276000,
  "accountsScope": "legal_entity",
  "url": "https://www.allabolag.se/5560743089",
  "equityRatio": 29.4,
  "fTaxRegistered": true,
  "fTaxDescription": "Ja, registrerad för F-skatt",
  "vatRegistered": true,
  "payrollTaxRegistered": true,
  "shareCapitalKSEK": 724889,
  "paymentRemarks": false,
  "announcements": [
    {
      "id": "990e3f217e62af71a3232d24e5e2d99226914d19",
      "date": "23.09.2026",
      "text": "Adress",
      "type": "CONTACT_ADDRESS"
    },
    {
      "id": "902c8d6dcaffc3fa9fc5f214483d66379de6a07b",
      "date": "28.05.2026",
      "text": "Årsredovisning",
      "type": "REGISTERED_ANNUAL_REPORT"
    },
    {
      "id": "8b20ad2ecaf8ed3612a140ced6d6d22fc698ffce",
      "date": "26.02.2026",
      "text": "Bransch",
      "type": "INDUSTRY"
    },
    {
      "id": "6b8f2fc19d44e1cdc975f9f60709a45f6a0af270",
      "date": "01.12.2025",
      "text": "Bransch",
      "type": "INDUSTRY"
    },
    {
      "id": "7510109e01bd8e5d91aafd863bae5ed88bbcf522",
      "date": "05.11.2025",
      "text": "Fusion övertagande företag",
      "type": "MERGER_EATER"
    },
    {
      "id": "203d2db19797fee668444672ab3b24b0e537a4e4",
      "date": "29.08.2025",
      "text": "Fusion övertagande företag",
      "type": "MERGER_EATER"
    },
    {
      "id": "2ca465d73347c223d2b9628f723d217b275d274b",
      "date": "17.05.2025",
      "text": "Årsredovisning",
      "type": "REGISTERED_ANNUAL_REPORT"
    },
    {
      "id": "ade8bea35728215f0287a25fc9d7d554843050ad",
      "date": "14.05.2025",
      "text": "Fusion övertagande företag",
      "type": "MERGER_EATER"
    },
    {
      "id": "cf9b8c0678975bbe296379586299cec257ec8f97",
      "date": "06.05.2025",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "a5c0695aa3547d6ef03296e05ebdfaaf2cf1c171",
      "date": "29.04.2025",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    }
  ],
  "signatories": [
    "Firman tecknas av styrelsen",
    "Firman tecknas två i förening av",
    "Fager, Hanna Viola",
    "Hansson, Karl Fredrik",
    "Hu, Yanhang",
    "Samuelsson, Håkan",
    "Dessutom har verkställande direktören rätt att teckna firman",
    "beträffande löpande förvaltningsåtgärder"
  ],
  "legalForm": "Aktiebolag",
  "companyFormCode": "Aktiebolag",
  "companyDescription": "Bolagets syfte är att erbjuda konsumenter frihet att färdas på ett personligt, hållbart och säkert sätt. För att uppnå detta syfte kommer bolaget både direkt och genom dotterbolag eller partnerskap utveckla, tillverka, marknadsföra och försälja bilar och erbjuda abonnemang på bilar och andra mobilitetstjänster för transport av människor och gods. Bolaget kommer även att bedriva annan verksamhet för att uppnå ovan syfte, både direkt och indirekt samt genom ägande i andra bolag.",
  "estimatedTurnover": "> 10000000",
  "turnoverYear": 2025,
  "gazelle": false,
  "mortgages": false,
  "parentCompanyName": "Volvo Car AB",
  "parentCompanyOrgNumber": "5568108988",
  "parentCompanyCountryCode": "SE",
  "numberOfSubsidiaries": 64,
  "numberOfCompaniesInGroup": 111,
  "shareholders": [
    {
      "name": "Volvo Car AB",
      "share": null,
      "numberOfShares": 1,
      "companyId": "5568108988"
    }
  ],
  "status": "ACTIVE",
  "registeredDate": "1960-10-28",
  "ceo": "Verkställande direktör",
  "ceoTitle": "Verkställande direktör",
  "ceoName": "Håkan Samuelsson",
  "chairmanName": "Håkan Samuelsson",
  "boardTitles": [
    "Ordförande",
    "Ledamot",
    "Ledamot",
    "Ledamot"
  ],
  "revenueGrowthPct": -19.3,
  "profitGrowthPct": -143.91,
  "fiscalYear": "2025",
  "accounts": [
    {
      "fiscalYear": "2025",
      "revenueKSEK": 244217000,
      "profitKSEK": -7843000,
      "equityRatio": 29.4,
      "employees": 20190,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2024",
      "revenueKSEK": 302609000,
      "profitKSEK": 17862000,
      "equityRatio": 30.8,
      "employees": 19317,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2023",
      "revenueKSEK": 300276000,
      "profitKSEK": 13443000,
      "equityRatio": 25.9,
      "employees": 19340,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2022",
      "revenueKSEK": 215905000,
      "profitKSEK": 5256000,
      "equityRatio": 23.1,
      "employees": 18858,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2021",
      "revenueKSEK": 203205000,
      "profitKSEK": 8050000,
      "equityRatio": 20.1,
      "employees": 17936,
      "accountsScope": "legal_entity"
    }
  ],
  "fetchedAt": "2026-11-16T19:08:29.866937Z"
}
```

## Run it from code
Python ([apify-client](https://pypi.org/project/apify-client/)):

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("redomic/allabolag-company-scraper").call(run_input={"sniCodes": ["62.10"], "sort": "revenueDesc"})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

curl (waits for the run and returns the rows):

```bash
curl -X POST "https://api.apify.com/v2/acts/redomic~allabolag-company-scraper/run-sync-get-dataset-items?token=$APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"sniCodes": ["62.10"], "sort": "revenueDesc"}'
```

## All inputs, modes and pricing
See the full documentation on the Apify page: [https://apify.com/redomic/allabolag-company-scraper](https://apify.com/redomic/allabolag-company-scraper)
