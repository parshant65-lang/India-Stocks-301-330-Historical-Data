# India-Stocks-301-330-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 301 to 330)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-301-330-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (301 to 330)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 301 | `CHOICEIN` | Choice International Ltd. | `CHOICEIN.NS` |
| 302 | `CHOLAHLDNG` | Cholamandalam Financial Holdings Ltd. | `CHOLAHLDNG.NS` |
| 303 | `CUB` | City Union Bank Ltd. | `CUB.NS` |
| 304 | `CLEANMAX` | Clean Max Enviro Energy Solutions Ltd. | `CLEANMAX.NS` |
| 305 | `CLEAN` | Clean Science and Technology Ltd. | `CLEAN.NS` |
| 306 | `COHANCE` | Cohance Lifesciences Ltd. | `COHANCE.NS` |
| 307 | `CAMS` | Computer Age Management Services Ltd. | `CAMS.NS` |
| 308 | `CONCORDBIO` | Concord Biotech Ltd. | `CONCORDBIO.NS` |
| 309 | `CRAFTSMAN` | Craftsman Automation Ltd. | `CRAFTSMAN.NS` |
| 310 | `CREDITACC` | CreditAccess Grameen Ltd. | `CREDITACC.NS` |
| 311 | `CROMPTON` | Crompton Greaves Consumer Electricals Ltd. | `CROMPTON.NS` |
| 312 | `CUPID` | Cupid Ltd. | `CUPID.NS` |
| 313 | `CYIENT` | Cyient Ltd. | `CYIENT.NS` |
| 314 | `DOMS` | DOMS Industries Ltd. | `DOMS.NS` |
| 315 | `DATAPATTNS` | Data Patterns (India) Ltd. | `DATAPATTNS.NS` |
| 316 | `DEEPAKFERT` | Deepak Fertilisers & Petrochemicals Corp. Ltd. | `DEEPAKFERT.NS` |
| 317 | `DEEPAKNTR` | Deepak Nitrite Ltd. | `DEEPAKNTR.NS` |
| 318 | `DELHIVERY` | Delhivery Ltd. | `DELHIVERY.NS` |
| 319 | `DEVYANI` | Devyani International Ltd. | `DEVYANI.NS` |
| 320 | `LALPATHLAB` | Dr. Lal Path Labs Ltd. | `LALPATHLAB.NS` |
| 321 | `DUMMYHEG` | Dummy HEG Ltd. | `DUMMYHEG.NS` |
| 322 | `EIDPARRY` | E.I.D. Parry (India) Ltd. | `EIDPARRY.NS` |
| 323 | `EIHOTEL` | EIH Ltd. | `EIHOTEL.NS` |
| 324 | `EMBASSY` | EMBASSY OFFICE PARKS REIT | `EMBASSY.NS` |
| 325 | `ELECON` | Elecon Engineering Co. Ltd. | `ELECON.NS` |
| 326 | `ELGIEQUIP` | Elgi Equipments Ltd. | `ELGIEQUIP.NS` |
| 327 | `EMAMILTD` | Emami Ltd. | `EMAMILTD.NS` |
| 328 | `EMCURE` | Emcure Pharmaceuticals Ltd. | `EMCURE.NS` |
| 329 | `EMMVEE` | Emmvee Photovoltaic Power Ltd. | `EMMVEE.NS` |
| 330 | `ENGINERSIN` | Engineers India Ltd. | `ENGINERSIN.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream CHOICEIN 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-301-330-Historical-Data/main/CHOICEIN/1m/2026/10/CHOICEIN_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
