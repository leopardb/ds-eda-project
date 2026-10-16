# King County Housing EDA Project

## Project overview

This project explores historical residential property sales in King County, Washington (USA), with a focus on luxury waterfront properties.

The goal is to use exploratory data analysis (EDA) to identify relevant market patterns and provide actionable recommendations for a fictional real estate client.

## Client: Jennifer Montgomery

Jennifer is a prospective buyer with the following requirements:

* High budget and preference for prestigious properties
* Waterfront location
* High construction quality (grade)
* Preferably already renovated
* Purchase within one month
* Intention to resell within one year

## Dataset and methodology

The project uses the King County Housing dataset, containing approximately 21,600 historical property sales.

The data was retrieved from a PostgreSQL database by joining two tables, then explored using Python and pandas.

The analysis includes:
* Data inspection and cleaning
* Missing-value handling and feature engineering
* Descriptive statistics and median price comparisons
* Geographic analysis using ZIP codes
* Data visualization with Matplotlib and Seaborn

For the purpose of this analysis, luxury properties are defined as houses with a grade of at least 10.

## Research questions and key findings


1. How does waterfront access affect luxury property prices?

Among properties with grade 10 or higher:
* Waterfront properties: $2.51M median sale price (57 transactions)
* Non-waterfront properties: $1.01M median sale price

Recommendation: Jennifer should anticipate a substantial price premium for luxury waterfront properties and prepare for a relatively narrow selection.

2. Which areas have the most historical luxury waterfront transactions?

ZIP codes **98040** and **98008** have the highest numbers of recorded transactions matching the luxury waterfront criteria, with 8 and 7 sales respectively.

Recommendation: Prioritize these two ZIP codes when searching for suitable properties, while independently checking current listings and local resale conditions.

Historical transaction counts alone do not establish market liquidity or guarantee a quick resale.

3. Are renovated luxury homes more expensive?

Among properties with grade 10 or higher:
* Renovated properties: $1.66M median sale price (59 transactions)
* Non-renovated properties or properties without recorded renovation: $1.01M median sale price (1,576 transactions)

The observed price difference generally persists when properties are grouped by living area, although some groups contain very few renovated properties.

Recommendation: Jennifer should prioritize already-renovated properties to meet her preferences and avoid immediate renovation work. However, she should evaluate the purchase price carefully, as a renovation premium does not guarantee profitable resale.

## Limitations

This analysis is exploratory and based on historical sales rather than current property listings.

Important limitations include:
* Historical sale prices do not predict future appreciation.
* Transaction counts do not measure time on market.
* Small sample sizes affect some luxury property comparisons.
* Missing waterfront and renovation values were treated as negative or unrecorded.
* Observed price differences do not establish causal relationships.

In particular, the dataset cannot establish whether Jennifer could profitably resell a property within one year.

## Repository structure


| File                                | Description                                                               |
| :---                                | :---                                                                      |
| `01_assignment.md`                  | Original project assignment and client descriptions                       |
| `02_workflow.md`                    | Recommended EDA workflow                                                  |
| `03_fetching_the_data_eda.ipynb`    | Database connection, SQL join and data retrieval                          |
| `04_eda.ipynb`                      | Main exploratory analysis, visualizations, findings and recommendations   |
| `column_names.md`                   | Dataset column descriptions                                               |
| `data/`                             | Local dataset directory; CSV data is excluded from Git                    |
| `pyproject.toml`                    | Python project configuration and dependencies                             |
| `uv.lock`                           | Locked dependency versions                                                |

## Running the project

Clone the repository:
```
git clone https://github.com/leopardb/ds-eda-project.git
cd ds-eda-project
```
Install the Python dependencies:

```
uv sync
```

The main analysis is contained in `04_eda.ipynb` and reads the locally stored dataset from `data/eda.csv`.

The original dataset is not committed to GitHub. Reproducing the analysis requires obtaining the dataset and placing it at that path. The data-retrieval notebook documents the PostgreSQL extraction process.

## Tools

Python · pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook · PostgreSQL · SQLAlchemy · Git

## Conclusion

Luxury waterfront properties command substantially higher historical sale prices, and certain ZIP codes show greater concentrations of matching transactions. Renovated luxury properties also tend to sell at higher prices.

For Jennifer, the recommended approach is to focus on high-grade waterfront properties in ZIP codes 98040 and 98008, favor already-renovated homes, and carefully assess short-term resale risk before purchasing.

The central finding is that prestige can be identified and priced using historical data, but profitable resale within one year cannot be guaranteed.
