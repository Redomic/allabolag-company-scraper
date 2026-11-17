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
  "orgNumber": "5560566258",
  "name": "Ericsson AB",
  "status": "ACTIVE",
  "marketingProtection": false,
  "registeredDate": "1952-03-11",
  "address": "Torshamnsgatan 21",
  "postalCode": "164 80",
  "postPlace": "Stockholm",
  "municipality": "Stockholm",
  "county": "Stockholm",
  "industry": "62100 Dataprogrammering",
  "sniCode": "62100",
  "sniName": "Dataprogrammering",
  "latitude": 59.40488536,
  "longitude": 17.95567733,
  "employees": 13052,
  "revenueKSEK": 134244000,
  "profitKSEK": 19602000,
  "accountsScope": "legal_entity",
  "url": "https://www.allabolag.se/5560566258",
  "equityRatio": 49.6,
  "fTaxRegistered": true,
  "fTaxDescription": "Ja, registrerad för F-skatt",
  "vatRegistered": true,
  "payrollTaxRegistered": true,
  "shareCapitalKSEK": 50000,
  "paymentRemarks": false,
  "announcements": [
    {
      "id": "a11fc1c73430ce5890563b586d7354584896d42b",
      "date": "27.10.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "b306832b81903e9f1035d0ea9baa2792b9f73dac",
      "date": "14.10.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "19f93c7453edd9cb3bf4741e23860e035e900a3f",
      "date": "16.09.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "3921ec0aca0b854128ab5101e352bdb07b5487da",
      "date": "25.08.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "10a2e5035d43ccf803f192a0cfbde358b7203fc3",
      "date": "22.07.2026",
      "text": "Årsredovisning",
      "type": "REGISTERED_ANNUAL_REPORT"
    },
    {
      "id": "4f9f1322b2254a6f901a46a22ac835b2066c8e64",
      "date": "08.06.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "ecbaf60e604eb0d6e834ec4bd60f4ef35344555c",
      "date": "03.06.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "735ab685e04024689fd584287ec3402e5e39cf33",
      "date": "08.04.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "3931739a97e3c0379b9c4d48bee35351739bb8cf",
      "date": "19.01.2026",
      "text": "Firmatecknare",
      "type": "SIGNATORY"
    },
    {
      "id": "7c894f2b88e13fccdc129ee9fd3725399539bb86",
      "date": "01.12.2025",
      "text": "Bransch",
      "type": "INDUSTRY"
    }
  ],
  "signatories": [
    "Firman tecknas av styrelsen",
    "Firman tecknas två i förening av",
    "Daberius, Stefan Otto",
    "Ekudden, Carl Erik Ingvar",
    "Hammarwall, David Oscar Andreas",
    "Hyllander, Nils Erik Johan",
    "Levert, Charlotte Marie",
    "Lindqvist, Jenny Elena",
    "Löfgren, Per Gunnar",
    "Narvinger, Per Andreas",
    "Nordéus, Magnus Gustav",
    "Sandström, Lars David",
    "Stenmark, Jakob Ingemar",
    "Stringberg, Karl Jonas Gustav",
    "eller en av dem",
    "i förening med en av",
    "Fidone, Salvatore Andrea",
    "Hultell, Sten Johan",
    "Lindberg, Lennart Martin Christer",
    "Petersson, Christina Cecilia",
    "Rydberg, Linda Maria",
    "Salentin, Stefan Herbert",
    "Vestergren, Anders Karl",
    "Dessutom har verkställande direktören rätt att teckna firman",
    "beträffande löpande förvaltningsåtgärder"
  ],
  "legalForm": "Aktiebolag",
  "companyFormCode": "Aktiebolag",
  "companyDescription": "Bolaget har till föremål för sin verksamhet att, direkt eller indirekt, utveckla, konstruera, tillverka, sälja och leverera samt i övrigt idka handel och annan näring med varor, produkter och övrig utrustning samt service, underhåll och andra tjänster baserat på telekommunikation och radioteknik samt andra tekniker för överföring, transmission och annan kommunikation av tal, data, bild, text, annan information och betalningsmedel samt att bedriva annan därmed förenlig verksamhet.",
  "estimatedTurnover": "> 10000000",
  "turnoverYear": 2025,
  "gazelle": false,
  "mortgages": false,
  "parentCompanyName": "Telefonaktiebolaget LM Ericsson",
  "parentCompanyOrgNumber": "5560160680",
  "parentCompanyCountryCode": "SE",
  "numberOfSubsidiaries": 2,
  "numberOfCompaniesInGroup": 58,
  "shareholders": [
    {
      "name": "Telefonaktiebolaget LM Ericsson",
      "share": null,
      "numberOfShares": 1,
      "companyId": "5560160680"
    }
  ],
  "ceo": "Verkställande direktör",
  "ceoTitle": "Verkställande direktör",
  "ceoName": "Per Gunnar Löfgren",
  "chairmanName": "Magnus Gustav Nordéus",
  "boardTitles": [
    "Ordförande",
    "Ledamot",
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
  "revenueGrowthPct": -3.73,
  "profitGrowthPct": 69.03,
  "fiscalYear": "2025",
  "accounts": [
    {
      "fiscalYear": "2025",
      "revenueKSEK": 134244000,
      "profitKSEK": 19602000,
      "equityRatio": 49.6,
      "employees": 13052,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2024",
      "revenueKSEK": 139441000,
      "profitKSEK": 11597000,
      "equityRatio": 38.3,
      "employees": 13529,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2023",
      "revenueKSEK": 125265353,
      "profitKSEK": -1154751,
      "equityRatio": 39.3,
      "employees": 14830,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2022",
      "revenueKSEK": 156326466,
      "profitKSEK": 21263028,
      "equityRatio": 49,
      "employees": 15296,
      "accountsScope": "legal_entity"
    },
    {
      "fiscalYear": "2021",
      "revenueKSEK": 142349064,
      "profitKSEK": 18065460,
      "equityRatio": 46.7,
      "employees": 14799,
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
          "amount": 989000
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 989000
        },
        {
          "code": "AK",
          "amount": 50000
        },
        {
          "code": "ANT",
          "amount": 13052
        },
        {
          "code": "avk_eget_kapital",
          "amount": 61.4
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 32.2
        },
        {
          "code": "RPE",
          "amount": 10285
        },
        {
          "code": "CPE",
          "amount": 1418
        },
        {
          "code": "DR",
          "amount": 19602000
        },
        {
          "code": "EKA",
          "amount": 49.6
        },
        {
          "code": "FI",
          "amount": 2878000
        },
        {
          "code": "FK",
          "amount": -1472000
        },
        {
          "code": "GG",
          "amount": 1.02
        },
        {
          "code": "KBP",
          "amount": 2239000
        },
        {
          "code": "LG",
          "amount": 13684000
        },
        {
          "code": "loner_ovriga",
          "amount": 13191000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 10000
        },
        {
          "code": "ORS",
          "amount": 24910000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 23291000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 24697000
        },
        {
          "code": "RG",
          "amount": 179.6
        },
        {
          "code": "SAP",
          "amount": 3803000
        },
        {
          "code": "SDI",
          "amount": 134244000
        },
        {
          "code": "SED",
          "amount": 81225000
        },
        {
          "code": "SI",
          "amount": 133255000
        },
        {
          "code": "SEK",
          "amount": 40249000
        },
        {
          "code": "SF",
          "amount": 8678000
        },
        {
          "code": "SFA",
          "amount": 5274000
        },
        {
          "code": "SGE",
          "amount": 81225000
        },
        {
          "code": "SIA",
          "amount": 733000
        },
        {
          "code": "SIK",
          "amount": 40189000
        },
        {
          "code": "SKG",
          "amount": 36754000
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -5308000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 75951000
        },
        {
          "code": "SUB",
          "amount": 19000000
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 1921000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 420000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -110954000
        },
        {
          "code": "SV",
          "amount": 9930000
        },
        {
          "code": "SVD",
          "amount": 2620000
        },
        {
          "code": "UTR",
          "amount": 0
        },
        {
          "code": "FSD",
          "amount": 213000
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
          "amount": 19.5
        },
        {
          "code": "EBITDA",
          "amount": 23291000
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
          "amount": 1529000
        },
        {
          "code": "ADK",
          "amount": 0
        },
        {
          "code": "ADR",
          "amount": 1529000
        },
        {
          "code": "AK",
          "amount": 50000
        },
        {
          "code": "ANT",
          "amount": 13529
        },
        {
          "code": "avk_eget_kapital",
          "amount": 42.1
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 18.2
        },
        {
          "code": "RPE",
          "amount": 10307
        },
        {
          "code": "CPE",
          "amount": 1581
        },
        {
          "code": "DR",
          "amount": 11597000
        },
        {
          "code": "EKA",
          "amount": 38.3
        },
        {
          "code": "FI",
          "amount": 2748000
        },
        {
          "code": "FK",
          "amount": -1668000
        },
        {
          "code": "GG",
          "amount": 1.61
        },
        {
          "code": "KBP",
          "amount": 2151000
        },
        {
          "code": "LG",
          "amount": 14551000
        },
        {
          "code": "loner_ovriga",
          "amount": 13824000
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 8000
        },
        {
          "code": "ORS",
          "amount": 15122000
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 11881000
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 12961000
        },
        {
          "code": "RG",
          "amount": 145.7
        },
        {
          "code": "SAP",
          "amount": 6884000
        },
        {
          "code": "SDI",
          "amount": 139441000
        },
        {
          "code": "SED",
          "amount": 80346000
        },
        {
          "code": "SI",
          "amount": 137912000
        },
        {
          "code": "SEK",
          "amount": 30786000
        },
        {
          "code": "SF",
          "amount": 7275000
        },
        {
          "code": "SFA",
          "amount": 6849000
        },
        {
          "code": "SGE",
          "amount": 80346000
        },
        {
          "code": "SIA",
          "amount": 452000
        },
        {
          "code": "SIK",
          "amount": 30726000
        },
        {
          "code": "SKG",
          "amount": 42602000
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -3525000
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 73497000
        },
        {
          "code": "SUB",
          "amount": 14000000
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 3318000
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 74000
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -127561000
        },
        {
          "code": "SV",
          "amount": 11448000
        },
        {
          "code": "SVD",
          "amount": 3079000
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
          "amount": 2162000
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 10.5
        },
        {
          "code": "EBITDA",
          "amount": 11881000
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
          "amount": 1045463
        },
        {
          "code": "ADK",
          "amount": -1631422
        },
        {
          "code": "ADR",
          "amount": 1045463
        },
        {
          "code": "AK",
          "amount": 50000
        },
        {
          "code": "ANT",
          "amount": 14830
        },
        {
          "code": "avk_eget_kapital",
          "amount": -13
        },
        {
          "code": "avk_totalt_kapital",
          "amount": -1.9
        },
        {
          "code": "RPE",
          "amount": 8447
        },
        {
          "code": "CPE",
          "amount": 1502
        },
        {
          "code": "DR",
          "amount": -1154751
        },
        {
          "code": "EKA",
          "amount": 39.3
        },
        {
          "code": "FI",
          "amount": 5118940
        },
        {
          "code": "FK",
          "amount": -2418150
        },
        {
          "code": "GG",
          "amount": 1.55
        },
        {
          "code": "KBP",
          "amount": 1811290
        },
        {
          "code": "LG",
          "amount": 12143958
        },
        {
          "code": "loner_ovriga",
          "amount": 15739148
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 10524
        },
        {
          "code": "ORS",
          "amount": -1661320
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": -6563879
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": -3863088
        },
        {
          "code": "RG",
          "amount": 134.3
        },
        {
          "code": "SAP",
          "amount": 7515622
        },
        {
          "code": "SDI",
          "amount": 125265353
        },
        {
          "code": "SED",
          "amount": 75608397
        },
        {
          "code": "SI",
          "amount": 124219890
        },
        {
          "code": "SEK",
          "amount": 29692353
        },
        {
          "code": "SF",
          "amount": 8359839
        },
        {
          "code": "SFA",
          "amount": 7187084
        },
        {
          "code": "SGE",
          "amount": 75608397
        },
        {
          "code": "SIA",
          "amount": 356708
        },
        {
          "code": "SIK",
          "amount": 29632353
        },
        {
          "code": "SKG",
          "amount": 38315450
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": 506569
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 68421313
        },
        {
          "code": "SUB",
          "amount": 0
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 2841695
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 84971
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -131829232
        },
        {
          "code": "SV",
          "amount": 16953803
        },
        {
          "code": "SVD",
          "amount": 3988681
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
          "amount": 2201768
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": -1.2
        },
        {
          "code": "EBITDA",
          "amount": -6563879
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
          "amount": 974021
        },
        {
          "code": "ADK",
          "amount": -2282187
        },
        {
          "code": "ADR",
          "amount": 974021
        },
        {
          "code": "AK",
          "amount": 50000
        },
        {
          "code": "ANT",
          "amount": 15296
        },
        {
          "code": "avk_eget_kapital",
          "amount": 31.8
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 17.8
        },
        {
          "code": "RPE",
          "amount": 10220
        },
        {
          "code": "CPE",
          "amount": 1261
        },
        {
          "code": "DR",
          "amount": 21263028
        },
        {
          "code": "EKA",
          "amount": 49
        },
        {
          "code": "FI",
          "amount": 5250744
        },
        {
          "code": "FK",
          "amount": -2650616
        },
        {
          "code": "GG",
          "amount": 1.04
        },
        {
          "code": "KBP",
          "amount": 2030763
        },
        {
          "code": "LG",
          "amount": 17662318
        },
        {
          "code": "loner_ovriga",
          "amount": 13542255
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 13581
        },
        {
          "code": "ORS",
          "amount": 26159084
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 16293167
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 18893296
        },
        {
          "code": "RG",
          "amount": 161.2
        },
        {
          "code": "SAP",
          "amount": 5559166
        },
        {
          "code": "SDI",
          "amount": 156326466
        },
        {
          "code": "SED",
          "amount": 121195921
        },
        {
          "code": "SI",
          "amount": 155352445
        },
        {
          "code": "SEK",
          "amount": 59368443
        },
        {
          "code": "SF",
          "amount": 11286477
        },
        {
          "code": "SFA",
          "amount": 7456247
        },
        {
          "code": "SGE",
          "amount": 121195921
        },
        {
          "code": "SIA",
          "amount": 437049
        },
        {
          "code": "SIK",
          "amount": 59308443
        },
        {
          "code": "SKG",
          "amount": 56187419
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -4896056
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 113739674
        },
        {
          "code": "SUB",
          "amount": 15000000
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 2561640
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 80893
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -140033300
        },
        {
          "code": "SV",
          "amount": 23168076
        },
        {
          "code": "SVD",
          "amount": 4457559
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
          "amount": 7265789
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 13.8
        },
        {
          "code": "EBITDA",
          "amount": 16293167
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
          "amount": 853071
        },
        {
          "code": "ADK",
          "amount": -2291491
        },
        {
          "code": "ADR",
          "amount": 853071
        },
        {
          "code": "AK",
          "amount": 50000
        },
        {
          "code": "ANT",
          "amount": 14799
        },
        {
          "code": "avk_eget_kapital",
          "amount": 37.8
        },
        {
          "code": "avk_totalt_kapital",
          "amount": 19.8
        },
        {
          "code": "RPE",
          "amount": 9619
        },
        {
          "code": "CPE",
          "amount": 1280
        },
        {
          "code": "DR",
          "amount": 18065460
        },
        {
          "code": "EKA",
          "amount": 46.7
        },
        {
          "code": "FI",
          "amount": 750217
        },
        {
          "code": "FK",
          "amount": -2416901
        },
        {
          "code": "GG",
          "amount": 1.14
        },
        {
          "code": "KBP",
          "amount": 2113120
        },
        {
          "code": "LG",
          "amount": 17583959
        },
        {
          "code": "loner_ovriga",
          "amount": 12936128
        },
        {
          "code": "loner_styrelse_vd",
          "amount": 16304
        },
        {
          "code": "ORS",
          "amount": 21756894
        },
        {
          "code": "resultat_e_avskrivningar",
          "amount": 21873382
        },
        {
          "code": "resultat_e_finansnetto",
          "amount": 20206697
        },
        {
          "code": "RG",
          "amount": 165.9
        },
        {
          "code": "SAP",
          "amount": 6777376
        },
        {
          "code": "SDI",
          "amount": 142349064
        },
        {
          "code": "SED",
          "amount": 114327603
        },
        {
          "code": "SI",
          "amount": 141495993
        },
        {
          "code": "SEK",
          "amount": 53424773
        },
        {
          "code": "SF",
          "amount": 9833800
        },
        {
          "code": "SFA",
          "amount": 7767519
        },
        {
          "code": "SGE",
          "amount": 114327603
        },
        {
          "code": "SIA",
          "amount": 679373
        },
        {
          "code": "SIK",
          "amount": 53364773
        },
        {
          "code": "SKG",
          "amount": 53988963
        },
        {
          "code": "SKGKI",
          "amount": 0
        },
        {
          "code": "SKO",
          "amount": -3691434
        },
        {
          "code": "SLG",
          "amount": 0
        },
        {
          "code": "SOM",
          "amount": 106560084
        },
        {
          "code": "SUB",
          "amount": 15000000
        },
        {
          "code": "summa_finansiella_anltillg",
          "amount": 2879274
        },
        {
          "code": "summa_langfristiga_skulder",
          "amount": 136491
        },
        {
          "code": "summa_rorelsekostnader",
          "amount": -120475682
        },
        {
          "code": "SV",
          "amount": 17014829
        },
        {
          "code": "SVD",
          "amount": 4208873
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
          "amount": 1550196
        },
        {
          "code": "IAC",
          "amount": 0
        },
        {
          "code": "TR",
          "amount": 15.9
        },
        {
          "code": "EBITDA",
          "amount": 21873382
        }
      ]
    }
  ],
  "fetchedAt": "2026-11-17T19:12:12.964970Z"
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
