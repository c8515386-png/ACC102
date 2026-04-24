# Women, Work, and Wealth: A WDI Analysis

## 1. Problem & Audience

**Problem**: Does economic growth automatically increase female labor force participation (LFP)? Or do other factors, such as education, matter more?

**Target Audience**: Policymakers, development economists, gender equality advocates

## 2. Data Source

- **Source**: World Bank World Development Indicators (WDI)
- **Access Method**: `pandas-datareader` API
- **Time Range**: 2000-2023
- **Countries**: 188 countries (with complete data for all 4 indicators)

### Key Indicators

| Indicator | Code | Description |
|-----------|------|-------------|
| Female Labor Force Participation | `SL.TLF.CACT.FE.ZS` | % of female population ages 15+ |
| Fertility Rate | `SP.DYN.TFRT.IN` | births per woman |
| GDP per capita | `NY.GDP.PCAP.CD` | current US$ |
| Female Literacy Rate | `SE.ADT.LITR.FE.ZS` | % of female population ages 15+ |

## 3. Methods

### Data Processing
- Missing value removal
- Outlier filtering (fertility: 0.5-10, LFP: 0-100, literacy: 0-100)
- Log transformation for GDP (skewed distribution)
- Income group classification using World Bank thresholds

### Analysis
- Cross-section analysis (2023 data)
- Correlation analysis by income group
- Time-series trends (2000-2023 for 6 representative countries)

### Visualizations
1. Fertility rate vs Female LFP (scatter plot by income group)
2. GDP per capita vs Female LFP (scatter plot by income group)
3. Correlation heatmap (4 indicators)
4. Violin plot (LFP distribution by income group)
5. Time trends (6 countries, LFP + fertility)
6. GDP vs Female literacy (scatter plot)

## 4. Key Findings

| Finding | Detail |
|---------|--------|
| **Weak GDP-LFP correlation** | Global r = -0.11 → growth alone doesn't guarantee female employment |
| **U-shaped hypothesis supported** | Low income: 58%, Middle: 48%, High: 54% |
| **Literacy matters more** | Literacy-LFP correlation (r = -0.14) > GDP-LFP correlation |
| **Literacy-income gap** | 38.6 percentage points gap between low and high income countries |
| **Extremes** | Highest LFP: Madagascar (83%), Lowest: Afghanistan (5%) |

## 5. How to Run
bash
pip install pandas pandas-datareader numpy matplotlib seaborn
jupyter notebook Women_Work_Wealth_Analysis.ipynb

6. Repository Structure

text
├── README.md                           # This file
├── Women_Work_Wealth_Analysis.ipynb    # Main analysis notebook
├── requirements.txt                    # Python dependencies
├── figures/                            # Generated visualizations
│   ├── fertility_vs_lfp.png
│   ├── gdp_vs_lfp.png
│   ├── correlation_matrix.png
│   ├── lfp_violin.png
│   ├── time_trends.png
│   └── gdp_vs_literacy.png
└── data/                               # (Empty - data fetched via API)

7. Limitations

Correlation ≠ causation: Cannot establish causal relationships
Data gaps: Some countries missing literacy data (reduced sample to 188 countries)
Cross-country comparison: Cultural and policy factors not captured
Recent data: Some indicators have delayed reporting for 2023

8. Demo Video
