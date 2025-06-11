# TB Analysis for Timor-Leste (2017-2023)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![R](https://img.shields.io/badge/R-4.5.0+-blue.svg)](https://www.r-project.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## Overview

This project conducts a comprehensive statistical analysis of tuberculosis (TB) incidence in Timor-Leste from 2017-2023, examining factors influencing TB evolution, global country clustering patterns, and providing evidence-based justification for public health interventions.

## Research Questions

1. **Factor Analysis**: What factors influence the evolution of tuberculosis incidence rate? Which variables have the greatest impact, and is the pattern consistent for Timor-Leste?

2. **Global Clustering**: In which group of countries is Timor-Leste positioned when conducting global-level clustering based on TB-related variables?

3. **Trend Analysis**: What has been the trend in Timor-Leste's TB incidence rate from 2018-2023 (project years)? How does it compare to global, regional, and similar countries' trends?

4. **Project Justification**: Is the design and investment of the TB project justified based on data analysis of awareness-raising, diagnostic techniques, and professional training?

## Datasets

The analysis utilizes multiple WHO TB datasets:

- **TB Burden Estimates**: Country-level burden estimates including incidence and mortality
- **TB Budget Data**: Financial data for tuberculosis programs since 2018
- **Community Engagement**: Community activities and engagement data for TB
- **Drug Resistance Surveillance**: DR-TB testing and surveillance data since 2017
- **Expenditure & Utilization**: Health service expenditure and utilization since 2017
- **Case Notifications**: Detailed case notification data (>2MB)
- **Policies & Services**: TB policies and services data for 2023

## Methodology

### Statistical Approaches

- **Multiple Linear Regression** with stepwise selection for factor identification
- **Hierarchical Clustering** with dendrograms for country grouping
- **Principal Component Analysis (PCA)** for dimensionality reduction
- **Time Series Analysis** for trend analysis and decomposition
- **Bayesian Methods** for uncertainty quantification
- **Multivariate Analysis** for complex relationship modeling

### Data Processing Pipeline

1. **Data Loading**: Integration of 7 WHO TB datasets
2. **Data Combination**: Intelligent merging on country-year-ISO3 keys
3. **Temporal Filtering**: Focus on 2017-2023 project period
4. **Country-Specific Cleaning**: Removal of variables with no Timor-Leste data
5. **Quality Assurance**: Comprehensive validation and verification

## Project Structure

```
tb-analysis/
├── data/                           # WHO TB datasets (CSV files)
│   ├── TB_burden_countries_*.csv
│   ├── TB_budget_*.csv
│   ├── TB_community_engagement_*.csv
│   ├── TB_dr_surveillance_*.csv
│   ├── TB_expenditure_utilisation_*.csv
│   ├── TB_notifications_*.csv
│   ├── TB_policies_services_*.csv
│   └── TB_data_dictionary_*.csv
├── output/                         # Analysis outputs
│   └── tb_combined_2017_2023.csv   # Cleaned and filtered dataset
├── tb_analysis.ipynb              # Main R Jupyter notebook
├── Pipfile                        # Python dependencies
├── Pipfile.lock                   # Locked dependency versions
└── README.md                      # This file
```

## Data Summary

- **Original Combined Dataset**: 9,567 rows × 448 variables
- **Filtered Dataset (2017-2023)**: 1,505 rows × 276 variables
- **Timor-Leste Specific Data**: 7 observations (2017-2023)
- **Countries Included**: 215 countries/territories
- **Key Variables**: TB incidence, mortality, case detection, budget, expenditure

## Usage

### Prerequisites

- R 4.5.0 or higher
- Required R packages: `dplyr`, `readr`, `tidyr`, `stringr`, `purrr`
- Jupyter with R kernel (optional, for notebook execution)

### Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/ibagur/tb-analysis.git
   cd tb-analysis
   ```

2. **Install R dependencies**:
   ```r
   install.packages(c("dplyr", "readr", "tidyr", "stringr", "purrr"))
   ```

3. **Run the analysis**:
   - Open `tb_analysis.ipynb` in Jupyter
   - Execute cells sequentially
   - Or run in R/RStudio directly

### Key Outputs

- **Cleaned Dataset**: `output/tb_combined_2017_2023.csv`
- **Analysis Results**: Generated within the Jupyter notebook
- **Visualizations**: Charts and plots for trend analysis and clustering

## Data Quality

### Dataset Cleaning Results
- **Removed**: 172 variables with no Timor-Leste data
- **Retained**: 276 relevant variables for analysis
- **Coverage**: 100% availability for key indicators (e_inc_100k, e_mort_100k)
- **Completeness**: 95%+ coverage for primary analysis variables

### Timor-Leste Specific Data
- **Complete Coverage**: 2017-2023 (7 years)
- **Key Indicators**: TB incidence, case detection rate, budget data
- **Data Quality**: High completeness for primary research variables

## Research Context

This analysis supports evidence-based evaluation of a tuberculosis intervention project implemented in Timor-Leste from 2018-2023, focusing on:

- **Awareness Raising**: Community engagement and education programs
- **Diagnostic Enhancement**: Improved identification and diagnostic techniques  
- **Professional Training**: Capacity building for healthcare workers
- **Program Effectiveness**: Data-driven assessment of intervention impact

## Contributing

This is an academic research project. For questions or collaboration inquiries, please open an issue or contact the repository maintainer.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **World Health Organization (WHO)** for providing comprehensive TB surveillance data
- **Timor-Leste Ministry of Health** for country-specific health system context
- **Academic Institution** supporting this research initiative

---

**Note**: This repository contains processed WHO data. Original data sources and citations are maintained within the analysis notebook.