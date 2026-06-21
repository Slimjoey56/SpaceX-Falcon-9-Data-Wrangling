# SpaceX-Falcon-9-Data-Wrangling
Data wrangling project using SpaceX Falcon 9 launch data to clean, transform, and prepare mission records for analysis and machine learning. The notebook explores launch sites, orbit frequencies, and landing outcomes, then creates a binary target variable to classify first-stage landing success using Python and Pandas.
# SpaceX Falcon 9 Data Wrangling

This project focuses on cleaning, transforming, and preparing historical launch data from SpaceX Falcon 9 missions for exploratory analysis and predictive modeling.

The notebook performs data wrangling tasks on launch records, analyzes mission outcomes, and creates a binary classification target to determine whether a first-stage landing was successful.

## Project Overview

Reusable first-stage boosters are a key factor in reducing launch costs. Understanding the factors that influence landing success enables more accurate predictions and supports data-driven decision-making.

This project:

* Loads and inspects SpaceX launch data
* Explores launch site distributions
* Analyzes orbital mission frequencies
* Examines mission outcome patterns
* Cleans and transforms raw data
* Creates a binary target variable (`Class`) for machine learning applications

## Dataset

The dataset contains historical Falcon 9 launch information, including:

* Flight number
* Launch date
* Launch site
* Payload mass
* Orbit type
* Booster version
* Mission outcome
* Landing outcome

## Technologies Used

* Python 3
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn

## Data Wrangling Tasks

### 1. Launch Site Analysis

Determine the number of launches conducted at each launch site.

```python
df['LaunchSite'].value_counts()
```

### 2. Orbit Analysis

Identify the frequency of launches for each orbit type.

```python
df['Orbit'].value_counts()
```

### 3. Mission Outcome Analysis

Examine the occurrence of different landing outcomes.

```python
landing_outcomes = df['Outcome'].value_counts()
```

### 4. Create a Classification Label

Convert landing outcomes into a binary target variable:

* `1` = Successful landing
* `0` = Unsuccessful landing

```python
landing_class = []

for outcome in df['Outcome']:
    if outcome in bad_outcomes:
        landing_class.append(0)
    else:
        landing_class.append(1)

df['Class'] = landing_class
```

Calculate the overall landing success rate:

```python
df['Class'].mean()
```

## Project Structure

```text
├── labs-jupyter-spacex-Data wrangling-v2.ipynb
├── dataset_part_1.csv
├── README.md
```

## Key Findings

* Falcon 9 launches originate from multiple launch sites with varying frequencies.
* Certain orbit types are more common than others.
* Landing outcomes vary significantly across missions.
* Approximately 66% of first-stage landings in the dataset were successful.

## Future Work

* Perform exploratory data analysis (EDA)
* Visualize launch trends and success rates
* Engineer additional features
* Build classification models to predict landing success
* Evaluate model performance using accuracy, precision, recall, and F1-score

## References

* SpaceX Falcon 9 launch data
* [SpaceX Official Website](https://www.spacex.com?utm_source=chatgpt.com)
* [IBM Data Science Professional Certificate](https://www.coursera.org/professional-certificates/ibm-data-science?utm_source=chatgpt.com)
* [SpaceX API Documentation](https://github.com/r-spacex/SpaceX-API?utm_source=chatgpt.com)

## Author

Jehosaphat Brobbey Impiani

GitHub: [Slimjoey56 GitHub Profile](https://github.com/Slimjoey56?utm_source=chatgpt.com)
LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/jehosaphat-brobbey-impiani-9797b8252?utm_source=chatgpt.com)
