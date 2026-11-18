# Allabolag Scraper: Swedish Company Data & Financials

Get Swedish companies from allabolag.se as a spreadsheet: organisation number, industry (SNI code), address, employees, revenue, profit, equity ratio, growth, CEO and board roles, and the tax and VAT registration status. Search by name or keyword, list every company in an industry and region, or follow the companies registered in Sweden this week.

**Run it in the cloud, no setup:** [https://apify.com/redomic/allabolag-company-scraper](https://apify.com/redomic/allabolag-company-scraper). Works on Apify's free plan; about $0.40 per 1,000 results
(less on paid plans). Schedules, API, webhooks and CSV/Excel/JSON export are built in.

## What you get
Every company registered under SNI 62.10 (software development), sorted by revenue, on 15 November 2026:

| Company | Org number | City | Employees | Revenue (MSEK) | Profit (MSEK) | Equity ratio | First seen | Last seen | Days tracked |
|---|---|---|---|---|---|---|---|---|---|
| Ericsson AB | 5560566258 | Stockholm | 13,052 | 134,244 | 19,602 | 49.6% | 2026-11-15 | 2026-11-15 | 0 |
| IFS World Operations AB | 5560406042 | Linköping | 553 | 7,448 | 1,022 | 45.5% | 2026-11-15 | 2026-11-15 | 0 |
| Tata Consultancy Services Sverige AB | 5565594008 | Stockholm | 211 | 5,567 | 405 | 60.5% | 2026-11-15 | 2026-11-15 | 0 |
| Embark Studios AB | 5591723019 | Stockholm | 318 | 3,821 | 364 | 17.9% | 2026-11-15 | 2026-11-15 | 0 |
| SAP Svenska AB | 5563229680 | Stockholm | 215 | 3,699 | 108 | 29.9% | 2026-11-15 | 2026-11-15 | 0 |
| Nasdaq Technology AB | 5563148138 | Stockholm | 993 | 2,656 | 365 | 77.1% | 2026-11-15 | 2026-11-15 | 0 |
| Consid AB | 5565994307 | Jönköping | 1,114 | 2,595 | 41 | 23.6% | 2026-11-15 | 2026-11-15 | 0 |

The three last columns come from a first run: `firstSeen` and `lastSeen` are both the run date and `daysTracked` is 0. If you schedule a task, every later run keeps `firstSeen`, moves `lastSeen` to the new date and grows `daysTracked`, so a list tells you how long you have been following each prospect. That history is ours, collected run by run in a named key-value store; it is not a field allabolag publishes and cannot be backfilled from a single scrape. Sole traders are left out, so no personal identity number is stored.

Each row also carries the legal form, registration date, status, full address, county, SNI code and name, a company description, estimated turnover, turnover year, gazelle and mortgage flags, revenue and profit growth, share capital, F-tax, VAT and payroll registration, payment remarks, parent company, the CEO and chair, and the last few years of accounts. The figures come in kSEK, as allabolag shows them.

Rows also carry `industries`: every SNI industry branch the company is registered under, not just the main one in `sniCode`, so you can screen by a secondary activity. It is left off rows where the source publishes no branch data; for Ericsson AB (org 5560566258) a detail run returns:

```json
"industries": [
  "62100 Dataprogrammering",
  "70100 Verksamheter som utövas av huvudkontor",
  "72109 Annan naturvetenskaplig och teknisk forskning och utveckling",
  "26300 Tillverkning av kommunikationsutrustning",
  "58290 Utgivning av annan programvara"
]
```

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
  "industries": [
    "29101 Tillverkning av personbilar och andra lätta motorfordon",
    "29200 Tillverkning av karosserier för motorfordon; tillverkning av släpfordon och påhängsvagnar",
    "46720 Partihandel med reservdelar och tillbehör till motorfordon",
    "27110 Tillverkning av elmotorer, generatorer och transformatorer",
    "72109 Annan naturvetenskaplig och teknisk forskning och utveckling",
    "38214 Återvinning av källsorterat material",
    "71200 Teknisk provning och analys",
    "62100 Dataprogrammering",
    "70100 Verksamheter som utövas av huvudkontor",
    "29320 Tillverkning av andra delar och tillbehör till motorfordon"
  ],
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
  "filedAccounts": [
    {
      "fiscalYear": "2025",
      "periodStart": "2025-01-01",
      "periodEnd": "2025-12-31",
      "currency": "SEK",
      "items": [
        {
          "code": "ADI",
          "amount": 195000
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 195000
        },
        {
          "code": "AK",
          "amount": 725000
        },
        {
          "code": "ANT",
          "amount": 20190
        },
        {
          "code": "avk_eget_kapital",
          "amount": -12.4
        },
        {
          "code": "avk_totalt_kapital",
          "amount": -2.3
        },
        {
          "code": "RPE",
          "amount": 12096
        },
        {
          "code": "CPE",
          "amount": 1078
        },
        {
          "code": "DR",
          "amount": -7843000
        },
        {
          "code": "EKA",
          "amount": 29.4
        },
        {
          "code": "FI",
          "amount": 3026000
        },
        {
          "code": "FK",
          "amount": -2606000
        },
        {
          "code": "GG",
          "amount": 2.4
        },
        {
          "code": "KBP",
          "amount": 48526000
        },
        {
          "code": "LG",
          "amount": 21153000
        },
        {
          "code": "loner_ovriga",
          "amount": 14296000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 118000
        },
        {
          "code": "ORS",
          "amount": -7276000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": -7696000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": -7276000
        },
        {
          "code": "RG",
          "amount": 89.3
        },
        {
          "code": "SAP",
          "amount": 9778000
        },
        {
          "code": "SDI",
          "amount": 244217000
        },
        {
          "code": "SED",
          "amount": 199998000
        },
        {
          "code": "SI",
          "amount": 244022000
        },
        {
          "code": "SEK",
          "amount": 58856000
        },
        {
          "code": "SF",
          "amount": 4461000
        },
        {
          "code": "SFA",
          "amount": 97924000
        },
        {
          "code": "SGE",
          "amount": 199998000
        },
        {
          "code": "SIA",
          "amount": 6429000
        },
        {
          "code": "SIK",
          "amount": 57835000
        },
        {
          "code": "SKG",
          "amount": 101976000
        },
        {
          "code": "SKGKI",
          "amount": 451000
        },
        {
          "code": "SKO",
          "amount": -567000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 102074000
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 73553000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 29388000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -251913000
        },
        {
          "code": "SV",
          "amount": 11029000
        },
        {
          "code": "SVD",
          "amount": 17942000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 0
        },
        {
          "code": "KB",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": -1.9
        },
        {
          "code": "EBITDA",
          "amount": -7696000
        }
      ]
    },
    {
      "fiscalYear": "2024",
      "periodStart": "2024-01-01",
      "periodEnd": "2024-12-31",
      "currency": "SEK",
      "items": [
        {
          "code": "ADI",
          "amount": 17507000
        },
        {
          "code": "ADK",
          "amount": -371000
        },
        {
          "code": "ADR",
          "amount": 17507000
        },
        {
          "code": "AK",
          "amount": 725000
        },
        {
          "code": "ANT",
          "amount": 19317
        },
        {
          "code": "avk_eget_kapital",
          "amount": 31.9
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 11.7
        },
        {
          "code": "RPE",
          "amount": 15665
        },
        {
          "code": "CPE",
          "amount": 1105
        },
        {
          "code": "DR",
          "amount": 17862000
        },
        {
          "code": "EKA",
          "amount": 30.8
        },
        {
          "code": "FI",
          "amount": 3740000
        },
        {
          "code": "FK",
          "amount": -3646000
        },
        {
          "code": "GG",
          "amount": 2.25
        },
        {
          "code": "KBP",
          "amount": 39701000
        },
        {
          "code": "LG",
          "amount": 24832000
        },
        {
          "code": "loner_ovriga",
          "amount": 14503000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 128000
        },
        {
          "code": "ORS",
          "amount": 18759000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 18665000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 18759000
        },
        {
          "code": "RG",
          "amount": 84.4
        },
        {
          "code": "SAP",
          "amount": 10178000
        },
        {
          "code": "SDI",
          "amount": 302609000
        },
        {
          "code": "SED",
          "amount": 190958000
        },
        {
          "code": "SI",
          "amount": 285102000
        },
        {
          "code": "SEK",
          "amount": 58766000
        },
        {
          "code": "SF",
          "amount": 4148000
        },
        {
          "code": "SFA",
          "amount": 99366000
        },
        {
          "code": "SGE",
          "amount": 190958000
        },
        {
          "code": "SIA",
          "amount": 6898000
        },
        {
          "code": "SIK",
          "amount": 57745000
        },
        {
          "code": "SKG",
          "amount": 98208000
        },
        {
          "code": "SKGKI",
          "amount": 664000
        },
        {
          "code": "SKO",
          "amount": -897000
        },
        {
          "code": "SLG",
          "amount": 569000
        },
        {
          "code": "SOM",
          "amount": 91592000
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 77171000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 23806000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -283944000
        },
        {
          "code": "SV",
          "amount": 8663000
        },
        {
          "code": "SVD",
          "amount": 15297000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 0
        },
        {
          "code": "KB",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 7.4
        },
        {
          "code": "EBITDA",
          "amount": 18665000
        }
      ]
    },
    {
      "fiscalYear": "2023",
      "periodStart": "2023-01-01",
      "periodEnd": "2023-12-31",
      "currency": "SEK",
      "items": [
        {
          "code": "ADI",
          "amount": 10998000
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 10998000
        },
        {
          "code": "AK",
          "amount": 725000
        },
        {
          "code": "ANT",
          "amount": 19340
        },
        {
          "code": "avk_eget_kapital",
          "amount": 28.3
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 8.7
        },
        {
          "code": "RPE",
          "amount": 15526
        },
        {
          "code": "CPE",
          "amount": 1137
        },
        {
          "code": "DR",
          "amount": 13443000
        },
        {
          "code": "EKA",
          "amount": 25.9
        },
        {
          "code": "FI",
          "amount": 5206000
        },
        {
          "code": "FK",
          "amount": -2753000
        },
        {
          "code": "GG",
          "amount": 2.86
        },
        {
          "code": "KBP",
          "amount": 32163000
        },
        {
          "code": "LG",
          "amount": 29041000
        },
        {
          "code": "loner_ovriga",
          "amount": 14762000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 99000
        },
        {
          "code": "ORS",
          "amount": 14618000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 12165000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 14618000
        },
        {
          "code": "RG",
          "amount": 77.1
        },
        {
          "code": "SAP",
          "amount": 12162000
        },
        {
          "code": "SDI",
          "amount": 300276000
        },
        {
          "code": "SED",
          "amount": 199590000
        },
        {
          "code": "SI",
          "amount": 289278000
        },
        {
          "code": "SEK",
          "amount": 51657000
        },
        {
          "code": "SF",
          "amount": 3512000
        },
        {
          "code": "SFA",
          "amount": 100735000
        },
        {
          "code": "SGE",
          "amount": 199590000
        },
        {
          "code": "SIA",
          "amount": 7553000
        },
        {
          "code": "SIK",
          "amount": 50636000
        },
        {
          "code": "SKG",
          "amount": 112980000
        },
        {
          "code": "SKGKI",
          "amount": 657000
        },
        {
          "code": "SKO",
          "amount": -1175000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 98855000
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 80615000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 22791000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -288111000
        },
        {
          "code": "SV",
          "amount": 11752000
        },
        {
          "code": "SVD",
          "amount": 12567000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 0
        },
        {
          "code": "KB",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 5.8
        },
        {
          "code": "EBITDA",
          "amount": 12165000
        }
      ]
    },
    {
      "fiscalYear": "2022",
      "periodStart": "2022-01-01",
      "periodEnd": "2022-12-31",
      "currency": "SEK",
      "items": [
        {
          "code": "ADI",
          "amount": 821000
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 821000
        },
        {
          "code": "AK",
          "amount": 725000
        },
        {
          "code": "ANT",
          "amount": 18858
        },
        {
          "code": "avk_eget_kapital",
          "amount": 16.3
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 4.6
        },
        {
          "code": "RPE",
          "amount": 11449
        },
        {
          "code": "CPE",
          "amount": 1105
        },
        {
          "code": "DR",
          "amount": 5256000
        },
        {
          "code": "EKA",
          "amount": 23.1
        },
        {
          "code": "FI",
          "amount": 9415000
        },
        {
          "code": "FK",
          "amount": -1378000
        },
        {
          "code": "GG",
          "amount": 3.33
        },
        {
          "code": "KBP",
          "amount": 38201000
        },
        {
          "code": "LG",
          "amount": 22506000
        },
        {
          "code": "loner_ovriga",
          "amount": 12241000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 131000
        },
        {
          "code": "ORS",
          "amount": 6438000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": -1599000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 6438000
        },
        {
          "code": "RG",
          "amount": 80.5
        },
        {
          "code": "SAP",
          "amount": 10097000
        },
        {
          "code": "SDI",
          "amount": 215905000
        },
        {
          "code": "SED",
          "amount": 171293000
        },
        {
          "code": "SI",
          "amount": 215084000
        },
        {
          "code": "SEK",
          "amount": 39539000
        },
        {
          "code": "SF",
          "amount": 4376000
        },
        {
          "code": "SFA",
          "amount": 85042000
        },
        {
          "code": "SGE",
          "amount": 171293000
        },
        {
          "code": "SIA",
          "amount": 7489000
        },
        {
          "code": "SIK",
          "amount": 38518000
        },
        {
          "code": "SKG",
          "amount": 95983000
        },
        {
          "code": "SKGKI",
          "amount": 592000
        },
        {
          "code": "SKO",
          "amount": -1182000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 86251000
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 66334000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 25674000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -217504000
        },
        {
          "code": "SV",
          "amount": 9009000
        },
        {
          "code": "SVD",
          "amount": 11219000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 0
        },
        {
          "code": "KB",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 3.6
        },
        {
          "code": "EBITDA",
          "amount": -1599000
        }
      ]
    },
    {
      "fiscalYear": "2021",
      "periodStart": "2021-01-01",
      "periodEnd": "2021-12-31",
      "currency": "SEK",
      "items": [
        {
          "code": "ADI",
          "amount": 7667000
        },
        {
          "code": "ADK",
          "amount": -346000
        },
        {
          "code": "ADR",
          "amount": 7667000
        },
        {
          "code": "AK",
          "amount": 725000
        },
        {
          "code": "ANT",
          "amount": 17936
        },
        {
          "code": "avk_eget_kapital",
          "amount": 32
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 7.5
        },
        {
          "code": "RPE",
          "amount": 11329
        },
        {
          "code": "CPE",
          "amount": 1011
        },
        {
          "code": "DR",
          "amount": 8050000
        },
        {
          "code": "EKA",
          "amount": 20.1
        },
        {
          "code": "FI",
          "amount": 735000
        },
        {
          "code": "FK",
          "amount": -1483000
        },
        {
          "code": "GG",
          "amount": 3.97
        },
        {
          "code": "KBP",
          "amount": 34909000
        },
        {
          "code": "LG",
          "amount": 20168000
        },
        {
          "code": "loner_ovriga",
          "amount": 12325000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 144000
        },
        {
          "code": "ORS",
          "amount": 9677000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 10051000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 9303000
        },
        {
          "code": "RG",
          "amount": 74.2
        },
        {
          "code": "SAP",
          "amount": 9115000
        },
        {
          "code": "SDI",
          "amount": 203205000
        },
        {
          "code": "SED",
          "amount": 144659000
        },
        {
          "code": "SI",
          "amount": 195538000
        },
        {
          "code": "SEK",
          "amount": 29118000
        },
        {
          "code": "SF",
          "amount": 5032000
        },
        {
          "code": "SFA",
          "amount": 74902000
        },
        {
          "code": "SGE",
          "amount": 144659000
        },
        {
          "code": "SIA",
          "amount": 5927000
        },
        {
          "code": "SIK",
          "amount": 28097000
        },
        {
          "code": "SKG",
          "amount": 85140000
        },
        {
          "code": "SKGKI",
          "amount": 424000
        },
        {
          "code": "SKO",
          "amount": -1627000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 69757000
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 58135000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 21286000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -193154000
        },
        {
          "code": "SV",
          "amount": 6620000
        },
        {
          "code": "SVD",
          "amount": 10840000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 0
        },
        {
          "code": "KB",
          "amount": 374000
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 5.3
        },
        {
          "code": "EBITDA",
          "amount": 10051000
        }
      ]
    }
  ],
  "fetchedAt": "2026-11-18T22:37:39.725048Z",
  "firstSeen": "2026-11-18",
  "lastSeen": "2026-11-18",
  "daysTracked": 0
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
