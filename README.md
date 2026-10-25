# UN-SDG East Africa Dashboard Project

*SDG monitoring and analytics dashboard supporting East African governance and policy decisions; Python.*

![category](https://img.shields.io/badge/category-monitoring-evaluation-8B5CF6?style=flat-square) ![language](https://img.shields.io/badge/language-Python-2563EB?style=flat-square) ![license](https://img.shields.io/badge/license-MIT-16A34A?style=flat-square) ![maintenance](https://img.shields.io/badge/maintenance-active-16A34A?style=flat-square) ![repo](https://img.shields.io/badge/repo-un--sdg--east--africa-111827?style=flat-square)

---

## 📌 Overview
This project builds a reproducible **data science + Power BI dashboard** to track progress on the United Nations Sustainable Development Goals (SDGs) across East African countries. It integrates open datasets from the UN, World Bank, WHO, and UNICEF, applies AI/ML forecasting, and delivers actionable insights for policymakers, NGOs, and donors.

## 🎯 Objectives
- Collect and harmonize official UN/World Bank indicators.
- Build a **star schema** for clean analytics.
- Apply **AI/ML models** (Prophet, anomaly detection, composite scoring).
- Visualize results in **Power BI** with interactive maps, KPIs, and forecasts.
- Provide transparent documentation and governance for reproducibility.

## 🌍 Scope
Countries covered: Kenya, Uganda, Tanzania, Rwanda, Burundi, South Sudan, and optionally DRC.  
Indicators: Health (SDG 3), Education (SDG 4), Water & Sanitation (SDG 6), Climate (SDG 13).

## 🛠️ Tech Stack
- **Python** (pandas 2.3.3, pyarrow 22.0.0, scikit-learn 1.7.2, prophet 1.2.1)
- **Virtual Environment** (.ds-env) for reproducibility
- **Power BI Desktop** for visualization
- **GitHub** for version control & CI/CD
- **Open-source tools**: Prefect (pipelines), MkDocs (documentation)

## 📊 Key Insights
- Forecasts show which countries are **on track vs. off track** for 2030 SDG targets.
- Anomaly detection highlights **sudden declines** in food security or health.
- Composite SDG Index enables **prioritization of funding** and interventions.
- Dashboards connect SDG data to **UN challenges** like famine, conflict, and climate shocks.

## 📂 Project Structure

```
un-sdg-eastafrica/
├─ src/                          # Python source code
│  ├─ ingest/                   # Data ingestion scripts
│  │  ├─ pull_un_sdg.py        # Fetch UN SDG Indicator data
│  │  └─ pull_worldbank.py     # Fetch World Bank population data
│  ├─ transform/                # Data transformation scripts
│  │  ├─ harmonize_units.py    # Standardize and clean data
│  │  └─ build_star_schema.py  # Create analytics-ready schema
│  └─ utils/
│     └─ io.py                  # Path configuration for data directories
├─ notebooks/                    # Jupyter notebooks for EDA & modeling
├─ data_raw/                     # Raw datasets (git-ignored)
│  ├─ un_sdg_3_2_1.json        # UN Under-5 mortality rate data
│  └─ wb_population.json        # World Bank population data
├─ data_curated/                 # Cleaned parquet/CSV files
│  ├─ sdg_3_2_1.parquet        # Standardized UN SDG data
│  ├─ dim_country.parquet       # Country dimension table
│  ├─ dim_time.parquet          # Time dimension table
│  ├─ dim_indicator.parquet     # Indicator dimension table
│  └─ fact_indicator.parquet    # Fact table with measures
├─ bi/                           # Power BI models and reports
├─ docs/                         # Documentation (dictionary, governance, runbook)
├─ requirements.txt              # Python package dependencies
├─ .env                          # Environment variables (git-ignored)
└─ README.md                     # This file
```

## 🚀 Quick Start

### 1. Clone & Setup
```bash
git clone https://github.com/collins-muchiri/un-sdg-east-africa.git
cd un-sdg-eastafrica
```

### 2. Create Virtual Environment
```bash
python -m venv .ds-env
.\.ds-env\Scripts\activate       # On Windows
source .ds-env/bin/activate      # On macOS/Linux
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run Data Ingestion
```bash
python src/ingest/pull_un_sdg.py
python src/ingest/pull_worldbank.py
```

### 5. Transform Data
```bash
python src/transform/harmonize_units.py
python src/transform/build_star_schema.py
```

### 6. Launch Jupyter
```bash
jupyter lab
```

## 📦 Dependencies
- **Data Processing**: pandas 2.3.3, numpy 2.3.5, scipy 1.16.3, pyarrow 22.0.0
- **Machine Learning**: scikit-learn 1.7.2, prophet 1.2.1, statsmodels 0.14.5
- **Visualization**: matplotlib 3.10.7, seaborn 0.13.2
- **Development**: black 25.11.0, flake8 7.3.0, isort 7.0.0, pre-commit 4.4.0
- **Configuration**: python-dotenv 1.2.1, pydantic 2.12.4

## 📋 Data Pipeline
1. **Ingest**: Fetch raw data from UN & World Bank APIs
2. **Harmonize**: Standardize units, handle nulls, add ISO codes
3. **Transform**: Build star schema for BI consumption
4. **Analyze**: EDA, anomaly detection, forecasting
5. **Visualize**: Power BI dashboards + insights export

## 📝 Environment Variables
Create a `.env` file in the project root:
```
DATA_DIR_RAW=./data_raw
DATA_DIR_CURATED=./data_curated
```

## 🤝 Contributing
1. Create a feature branch (`git checkout -b feature/your-feature`)
2. Commit changes (`git commit -m "Add your feature"`)
3. Push to branch (`git push origin feature/your-feature`)
4. Open a Pull Request

## 📄 License
See `LICENSE` file for details.

## 📧 Contact
For questions or collaboration, contact the project maintainers on GitHub.

## Contribution and license

Issues and pull requests are welcome — please open an issue describing the proposed change before submitting substantive work. This project is released under the MIT License.
