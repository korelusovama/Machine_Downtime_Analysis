# Machine Downtime — Production and Operator Performance Dashboard

## Project overview

This project uses the [Maven Analytics — Machine Downtime](https://mavenanalytics.io/data-playground/manufacturing-downtime) dataset to analyze production performance, downtime causes, and operator-related downtime using **Microsoft Power BI**.

The dashboard was designed from an operations-management perspective, focusing on two main areas:

* **Production performance** — overall output, uptime, downtime trends, downtime causes, and product-level production efficiency.
* **Operator performance** — operator-controllable time, operator-caused downtime, error types, and production efficiency relative to standard production time.

The objective was not only to visualize the data, but to create a dashboard that helps identify **where production time is being lost and which areas may warrant further investigation**.

---

## Skills demonstrated

* Data cleaning and transformation using **Power Query**
* Data modeling
* **DAX** measures and KPI development
* Time-series analysis
* Pareto analysis
* Conditional formatting
* Business-oriented dashboard design

---

## Dashboard

The Power BI dashboard consists of views focused on **production performance** and **operator performance**.

![Production Performance Dashboard](images/Dashboard_Production%20performance.PNG)

![Operator Performance Dashboard](images/Dashboard_Operator%20performance.PNG)

---

## Key findings

The analysis identified several notable patterns in the observed production data:

* **38 batches** were produced during the observed period.
* The production process recorded approximately **41 hours of uptime** and **23 hours of downtime**, resulting in an overall downtime rate of approximately **36%**.
* The **five largest downtime causes account for approximately 80% of total recorded downtime**, making them the primary areas for further investigation.
* **Machine adjustment** is the largest individual contributor to recorded downtime.
* Approximately **56% of recorded downtime is classified as operator-caused**.
* **OR-600** has the largest production-time variance, with actual production time approximately **125% above standard production time**.
* Operator effectiveness ranges from approximately **73% to 77%** among the operators shown in the analysis.

---

## Potential areas for improvement

The findings suggest several areas that could be investigated further:

### 1. Machine adjustment

Machine adjustment is the largest contributor to downtime. Further investigation could determine whether these losses are associated with particular products, machines, or operating procedures.

### 2. Operator-caused downtime

More than half of recorded downtime is classified as operator-caused. Reviewing the frequency and duration of individual error types could help identify recurring issues that may potentially be addressed through training, process improvements, or other interventions.

### 3. OR-600 production-time variance

OR-600 has substantially higher actual production time than its standard production time. Investigating the reasons behind this variance could help identify a product-specific production constraint.

### 4. High-impact downtime causes

A relatively small number of downtime causes account for approximately 80% of total downtime. Improvement efforts could therefore initially focus on understanding these high-contribution causes rather than addressing every downtime category equally.

---

## Key metric definitions

### Downtime rate (%)

`
Total downtime ÷ Total observed production time × 100
`

This represents the proportion of total observed production time that was recorded as downtime.

### Time variance (%)

`
(Actual production time − Standard production time)
÷ Standard production time × 100
`

A positive value indicates that actual production time exceeded the standard production time.

### Operator effectiveness (%)

`
Standard production time ÷ Operator-controllable time × 100
`

This metric compares the standard production time with the amount of time considered controllable by the operator.

---

## Data preparation

The following data preparation and modeling steps were performed using **Power Query** and **Power BI**:

* Checked data continuity, missing values, duplicate records, data types, and potential outliers.
* Unpivoted downtime-factor columns to create a more analysis-friendly data structure.
* Added a calculated *Duration (min)* column based on start and end times.
* Renamed selected columns to improve readability within the data model.
* Added a dedicated **date table** for time-based analysis.
* Created **DAX measures** for key performance indicators and dashboard calculations.

---

## Assumptions and limitations

The source dataset does not provide explicit operational targets for production output, downtime, or operator performance. Where appropriate, internal averages have been used to visualize **relative performance within the dataset**.

The dataset is also relatively small and covers only a short observation period. As a result:
* Average-based metrics may be unreliable when calculated from very few observations (e.g., only one batch of a product).
* The short observation period does not provide sufficient data to reliably identify or analyze longer-term time trends.

---

## Dataset

The project uses the publicly available *Machine Downtime* dataset from *Maven Analytics*, which contains four tables of production-related data.

**Source:** [Maven Analytics — Machine Downtime](https://mavenanalytics.io/data-playground/manufacturing-downtime)

---

## Tools

* **Microsoft Power BI**
* **Power Query**
* **DAX**
* **Microsoft Excel** — initial data inspection
* **Git / GitHub** — version control and project documentation
