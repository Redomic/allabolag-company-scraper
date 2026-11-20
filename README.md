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

The first run keeps this table clean. Save it as a scheduled task and every later run adds `firstSeen`, `lastSeen` and `daysTracked` in a separate History view, keeping the original `firstSeen`, moving `lastSeen` to the new date and growing `daysTracked`, so a list tells you how long you have been following each prospect. That history is ours, collected run by run in a named key-value store; it is not a field allabolag publishes and cannot be backfilled from a single scrape. Sole traders are left out, so no personal identity number is stored.

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
  "orgNumber": "5567679849",
  "name": "SWECO Sverige AB",
  "marketingProtection": false,
  "address": "Gjörwellsgatan 22",
  "postalCode": "100 26",
  "postPlace": "Stockholm",
  "municipality": "Stockholm",
  "county": "Stockholm",
  "industry": "71121 Teknisk konsultverksamhet inom bygg- och anläggningsteknik",
  "sniCode": "71121",
  "sniName": "Teknisk konsultverksamhet inom bygg- och anläggningsteknik",
  "latitude": 59.3280736571709,
  "longitude": 18.0180503351969,
  "employees": 6303,
  "revenueKSEK": 9156670,
  "profitKSEK": 970930,
  "accountsScope": "legal_entity",
  "url": "https://www.allabolag.se/5567679849",
  "equityRatio": 45.2,
  "fTaxRegistered": true,
  "fTaxDescription": "Ja, registrerad för F-skatt",
  "vatRegistered": true,
  "payrollTaxRegistered": true,
  "shareCapitalKSEK": 129200,
  "paymentRemarks": false,
  "announcements": [
    {
      "id": "b08d5e98cc8c3c36849b1e1bdf68a806cf68b645",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "636fc0e519003b05fd96f7c82c9bb1feb232a84e",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "6f0e9beeb27ff7cd7c81e58c08d2788de31b3ca3",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "79a86584b95090592f6b034c494ab3131095f486",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "567ddc6f409ae621bd24b58f74ff25896b16cf03",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "b37cf17f5f7052d1d0417e86a12dcac5a710165d",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "6f60593aa17b40d68428271dbafce979a1807afe",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "0de6ee71762a6ab003e0139031a6a5183e0baa1a",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "e8ebd9c3c70635bc0f84013a3834eb3c56d65e99",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    },
    {
      "id": "49933ead3a70e8eebd747d630ea1ea097101b108",
      "date": "21.10.2026",
      "text": "Särskilt företagsnamn",
      "type": "SECONDARY_BUSINESS_NAME"
    }
  ],
  "signatories": [
    "Firman tecknas av styrelsen",
    "Firman tecknas två i förening av",
    "Allde, Jan Lennart",
    "Bergman, Åsa Anna Maria",
    "Wallner, Sture Fredrik",
    "Firman tecknas av en av",
    "Axby, Per Fredrik",
    "Bergström Sahlin, Ulla Elisabet",
    "Graveus, Frank",
    "Lindqvist, Torsten Magnus",
    "Norén, Mats Johan Gunnar",
    "Rosén, Anna Kajsa",
    "i",
    "förening med en av",
    "Allde, Jan Lennart",
    "Bergman, Åsa Anna Maria",
    "Karlsson, Lars Magnus Gunnar",
    "Wallner, Sture Fredrik",
    "Dessutom har verkställande direktören rätt att teckna firman",
    "beträffande löpande förvaltningsåtgärder"
  ],
  "legalForm": "Aktiebolag",
  "companyFormCode": "Aktiebolag",
  "industries": [
    "71121 Teknisk konsultverksamhet inom bygg- och anläggningsteknik",
    "71124 Teknisk konsultverksamhet inom energi-, miljö- och VVS-teknik",
    "71123 Teknisk konsultverksamhet inom elteknik",
    "71110 Arkitektverksamhet",
    "71129 Övrig teknisk konsultverksamhet",
    "63100 Datainfrastruktur, databehandling, hosting o.d.",
    "71122 Teknisk konsultverksamhet inom industriteknik"
  ],
  "companyDescription": "Bolaget ska, direkt eller indirekt genom hel- eller delägda bolag, bedriva konsultverksamhet inom områdena järnväg och annan spårbunden trafik, trafik- och transport i övrigt, arkitektur, anläggningsteknik, bygg- och byggnadsteknik och byggplanering, energisystem, el- och värmeteknik, telekommunikation, luft-, vatten-, mark-, och miljöteknik, maskinteknik, industriell process- och produktionsteknik, brandteknik, säkerhet, tekniska installationer inom VVS, el, tele och automation, näringspolitik och st= rukturomvandling, ekonomi, organisations- och personalutveckling samt leverera tjänster och produkter inom området geografiska och andra informationssystem samt bedriva därmed förenling verksamhet.",
  "estimatedTurnover": "5000000 - 9999999",
  "turnoverYear": 2025,
  "gazelle": false,
  "mortgages": false,
  "parentCompanyName": "SWECO Sverige Holding AB",
  "parentCompanyOrgNumber": "5560322496",
  "parentCompanyCountryCode": "SE",
  "numberOfSubsidiaries": 1,
  "numberOfCompaniesInGroup": 21,
  "shareholders": [
    {
      "name": "SWECO Sverige Holding AB",
      "share": null,
      "numberOfShares": 1,
      "companyId": "5560322496"
    }
  ],
  "status": "ACTIVE",
  "registeredDate": "2008-10-22",
  "ceo": "Verkställande direktör",
  "ceoTitle": "Verkställande direktör",
  "ceoName": "Sture Fredrik Wallner",
  "chairmanName": "Åsa Anna Maria Bergman",
  "boardTitles": [
    "Ordförande",
    "Ledamot",
    "Ledamot",
    "Ledamot",
    "Ledamot",
    "Ledamot",
    "Ledamot",
    "Suppleant",
    "Suppleant",
    "Suppleant"
  ],
  "revenueGrowthPct": -1.37,
  "profitGrowthPct": 213.93,
  "fiscalYear": "2025",
  "accounts": [
    {
      "fiscalYear": "2025",
      "revenueKSEK": 9156670,
      "profitKSEK": 49005,
      "equityRatio": 45.2,
      "employees": 6303,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2024",
      "revenueKSEK": 9283431,
      "profitKSEK": 15610,
      "equityRatio": 41.4,
      "employees": 6347,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2023",
      "revenueKSEK": 8585455,
      "profitKSEK": 204190,
      "equityRatio": 39.4,
      "employees": 6193,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2022",
      "revenueKSEK": 7967780,
      "profitKSEK": 109,
      "equityRatio": 35.1,
      "employees": 5823,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2021",
      "revenueKSEK": 7599145,
      "profitKSEK": 1738,
      "equityRatio": 37.8,
      "employees": 5706,
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
          "amount": 1717
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 1717
        },
        {
          "code": "AK",
          "amount": 129200
        },
        {
          "code": "ANT",
          "amount": 6303
        },
        {
          "code": "avk_eget_kapital",
          "amount": 58.5
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 26.5
        },
        {
          "code": "RPE",
          "amount": 1453
        },
        {
          "code": "CPE",
          "amount": 949
        },
        {
          "code": "DR",
          "amount": 49005
        },
        {
          "code": "EK",
          "amount": -84889
        },
        {
          "code": "EKA",
          "amount": 45.2
        },
        {
          "code": "FI",
          "amount": 32935
        },
        {
          "code": "FK",
          "amount": -472
        },
        {
          "code": "GG",
          "amount": 1.21
        },
        {
          "code": "KBP",
          "amount": 18627
        },
        {
          "code": "LG",
          "amount": 197841
        },
        {
          "code": "loner_ovriga",
          "amount": 4026119
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 5508
        },
        {
          "code": "ORS",
          "amount": 67660
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 938467
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 970930
        },
        {
          "code": "RG",
          "amount": 151.9
        },
        {
          "code": "SAP",
          "amount": 92284
        },
        {
          "code": "SDI",
          "amount": 9156670
        },
        {
          "code": "SED",
          "amount": 3669789
        },
        {
          "code": "SI",
          "amount": 9154953
        },
        {
          "code": "SEK",
          "amount": 1644071
        },
        {
          "code": "SF",
          "amount": 1384486
        },
        {
          "code": "SFA",
          "amount": 760201
        },
        {
          "code": "SGE",
          "amount": 3669789
        },
        {
          "code": "SIA",
          "amount": 57765
        },
        {
          "code": "SIK",
          "amount": 1495138
        },
        {
          "code": "SKG",
          "amount": 1914912
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -18655
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 2909588
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 564849
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 0
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -8218202
        },
        {
          "code": "SV",
          "amount": 1330
        },
        {
          "code": "SVD",
          "amount": 137587
        },
        {
          "code": "UTR",
          "amount": 18522
        },
        {
          "code": "FSD",
          "amount": -903271
        },
        {
          "code": "KB",
          "amount": 0
        },
        {
          "code": "AWA",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "BE",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 10.6
        },
        {
          "code": "EBITDA",
          "amount": 1023356
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
          "amount": 1126
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 1126
        },
        {
          "code": "AK",
          "amount": 129200
        },
        {
          "code": "ANT",
          "amount": 6347
        },
        {
          "code": "avk_eget_kapital",
          "amount": 66.1
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 27.4
        },
        {
          "code": "RPE",
          "amount": 1463
        },
        {
          "code": "CPE",
          "amount": 929
        },
        {
          "code": "DR",
          "amount": 15610
        },
        {
          "code": "EK",
          "amount": -89057
        },
        {
          "code": "EKA",
          "amount": 41.4
        },
        {
          "code": "FI",
          "amount": 59375
        },
        {
          "code": "FK",
          "amount": -441
        },
        {
          "code": "GG",
          "amount": 1.42
        },
        {
          "code": "KBP",
          "amount": 31317
        },
        {
          "code": "LG",
          "amount": 176771
        },
        {
          "code": "loner_ovriga",
          "amount": 3949149
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 4891
        },
        {
          "code": "ORS",
          "amount": 32761
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 1000580
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 1059513
        },
        {
          "code": "RG",
          "amount": 166.1
        },
        {
          "code": "SAP",
          "amount": 92902
        },
        {
          "code": "SDI",
          "amount": 9283431
        },
        {
          "code": "SED",
          "amount": 3872296
        },
        {
          "code": "SI",
          "amount": 9282305
        },
        {
          "code": "SEK",
          "amount": 1589802
        },
        {
          "code": "SF",
          "amount": 1362595
        },
        {
          "code": "SFA",
          "amount": 258589
        },
        {
          "code": "SGE",
          "amount": 3872296
        },
        {
          "code": "SIA",
          "amount": 86264
        },
        {
          "code": "SIK",
          "amount": 1440869
        },
        {
          "code": "SKG",
          "amount": 2174170
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -17151
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 3613706
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 37106
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 0
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -8282852
        },
        {
          "code": "SV",
          "amount": 2074
        },
        {
          "code": "SVD",
          "amount": 135220
        },
        {
          "code": "UTR",
          "amount": 15422
        },
        {
          "code": "FSD",
          "amount": 3248
        },
        {
          "code": "KB",
          "amount": -1030000
        },
        {
          "code": "AWA",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "BE",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 11.4
        },
        {
          "code": "EBITDA",
          "amount": 1089637
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
          "amount": 1160
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 1160
        },
        {
          "code": "AK",
          "amount": 129200
        },
        {
          "code": "ANT",
          "amount": 6193
        },
        {
          "code": "avk_eget_kapital",
          "amount": 77
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 30.3
        },
        {
          "code": "RPE",
          "amount": 1386
        },
        {
          "code": "CPE",
          "amount": 888
        },
        {
          "code": "DR",
          "amount": 204190
        },
        {
          "code": "EK",
          "amount": -83291
        },
        {
          "code": "EKA",
          "amount": 39.4
        },
        {
          "code": "FI",
          "amount": 50393
        },
        {
          "code": "FK",
          "amount": -535
        },
        {
          "code": "GG",
          "amount": 1.54
        },
        {
          "code": "KBP",
          "amount": 24274
        },
        {
          "code": "LG",
          "amount": 221330
        },
        {
          "code": "loner_ovriga",
          "amount": 3683962
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 4595
        },
        {
          "code": "ORS",
          "amount": 269758
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 920494
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 970353
        },
        {
          "code": "RG",
          "amount": 150.2
        },
        {
          "code": "SAP",
          "amount": 8123
        },
        {
          "code": "SDI",
          "amount": 8585455
        },
        {
          "code": "SED",
          "amount": 3199535
        },
        {
          "code": "SI",
          "amount": 8584295
        },
        {
          "code": "SEK",
          "amount": 1245183
        },
        {
          "code": "SF",
          "amount": 1376599
        },
        {
          "code": "SFA",
          "amount": 301561
        },
        {
          "code": "SGE",
          "amount": 3199535
        },
        {
          "code": "SIA",
          "amount": 100077
        },
        {
          "code": "SIK",
          "amount": 1096250
        },
        {
          "code": "SKG",
          "amount": 1927559
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -65568
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 2897973
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 62715
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 0
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -7664961
        },
        {
          "code": "SV",
          "amount": 2266
        },
        {
          "code": "SVD",
          "amount": 138769
        },
        {
          "code": "UTR",
          "amount": 18670
        },
        {
          "code": "FSD",
          "amount": -595
        },
        {
          "code": "KB",
          "amount": -700000
        },
        {
          "code": "AWA",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "BE",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 11.3
        },
        {
          "code": "EBITDA",
          "amount": 1003785
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
          "amount": 0
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 0
        },
        {
          "code": "AK",
          "amount": 129200
        },
        {
          "code": "ANT",
          "amount": 5823
        },
        {
          "code": "avk_eget_kapital",
          "amount": 79.1
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 27.8
        },
        {
          "code": "RPE",
          "amount": 1368
        },
        {
          "code": "CPE",
          "amount": 864
        },
        {
          "code": "DR",
          "amount": 109
        },
        {
          "code": "EK",
          "amount": -59522
        },
        {
          "code": "EKA",
          "amount": 35.1
        },
        {
          "code": "FI",
          "amount": 10795
        },
        {
          "code": "FK",
          "amount": -354
        },
        {
          "code": "GG",
          "amount": 1.85
        },
        {
          "code": "KBP",
          "amount": 17500
        },
        {
          "code": "LG",
          "amount": 216813
        },
        {
          "code": "loner_ovriga",
          "amount": 3355011
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 4310
        },
        {
          "code": "ORS",
          "amount": 16696
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 824446
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 834887
        },
        {
          "code": "RG",
          "amount": 141.2
        },
        {
          "code": "SAP",
          "amount": 4544
        },
        {
          "code": "SDI",
          "amount": 7967780
        },
        {
          "code": "SED",
          "amount": 3004320
        },
        {
          "code": "SI",
          "amount": 7967780
        },
        {
          "code": "SEK",
          "amount": 1040685
        },
        {
          "code": "SF",
          "amount": 1123939
        },
        {
          "code": "SFA",
          "amount": 262574
        },
        {
          "code": "SGE",
          "amount": 3004320
        },
        {
          "code": "SIA",
          "amount": 52971
        },
        {
          "code": "SIK",
          "amount": 891752
        },
        {
          "code": "SKG",
          "amount": 1941016
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -16587
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 2741746
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 72898
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 0
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -7143334
        },
        {
          "code": "SV",
          "amount": 2082
        },
        {
          "code": "SVD",
          "amount": 136705
        },
        {
          "code": "UTR",
          "amount": 18075
        },
        {
          "code": "FSD",
          "amount": 12609
        },
        {
          "code": "KB",
          "amount": -830800
        },
        {
          "code": "AWA",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "BE",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 10.5
        },
        {
          "code": "EBITDA",
          "amount": 883968
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
          "amount": 3379
        },
        {
          "code": "ADK",
          "amount": -12
        },
        {
          "code": "ADR",
          "amount": 3379
        },
        {
          "code": "AK",
          "amount": 129200
        },
        {
          "code": "ANT",
          "amount": 5706
        },
        {
          "code": "avk_eget_kapital",
          "amount": 53.6
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 20.3
        },
        {
          "code": "RPE",
          "amount": 1332
        },
        {
          "code": "CPE",
          "amount": 860
        },
        {
          "code": "DR",
          "amount": 1738
        },
        {
          "code": "EK",
          "amount": -57439
        },
        {
          "code": "EKA",
          "amount": 37.8
        },
        {
          "code": "FI",
          "amount": 18085
        },
        {
          "code": "FK",
          "amount": -656
        },
        {
          "code": "GG",
          "amount": 1.65
        },
        {
          "code": "KBP",
          "amount": 3
        },
        {
          "code": "LG",
          "amount": 167020
        },
        {
          "code": "loner_ovriga",
          "amount": 3271491
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 4020
        },
        {
          "code": "ORS",
          "amount": 6901
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 547108
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 564537
        },
        {
          "code": "RG",
          "amount": 150.3
        },
        {
          "code": "SAP",
          "amount": 3718
        },
        {
          "code": "SDI",
          "amount": 7599145
        },
        {
          "code": "SED",
          "amount": 2788617
        },
        {
          "code": "SI",
          "amount": 7595766
        },
        {
          "code": "SEK",
          "amount": 1029734
        },
        {
          "code": "SF",
          "amount": 1163063
        },
        {
          "code": "SFA",
          "amount": 195485
        },
        {
          "code": "SGE",
          "amount": 2788617
        },
        {
          "code": "SIA",
          "amount": 20869
        },
        {
          "code": "SIK",
          "amount": 880801
        },
        {
          "code": "SKG",
          "amount": 1724226
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -5163
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 2593132
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 50685
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 255
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -7052037
        },
        {
          "code": "SV",
          "amount": 1431
        },
        {
          "code": "SVD",
          "amount": 123931
        },
        {
          "code": "UTR",
          "amount": 30684
        },
        {
          "code": "FSD",
          "amount": -22636
        },
        {
          "code": "KB",
          "amount": -535000
        },
        {
          "code": "AWA",
          "amount": 0
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "BE",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 7.4
        },
        {
          "code": "EBITDA",
          "amount": 604547
        }
      ]
    }
  ],
  "fetchedAt": "2026-11-19T19:18:59.842525Z"
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
