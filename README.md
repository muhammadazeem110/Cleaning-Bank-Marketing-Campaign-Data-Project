# Cleaning Bank Marketing Campaign Data

## Project Description

### Objective
The goal of this project is to enhance the data management capabilities of a financial institution by refining and structuring the data collected from a recent marketing campaign. The bank aims to encourage customers to apply for personal loans, and the cleaned data will be used to establish a PostgreSQL database for storing and analyzing current and future campaign data.

## Process Overview
The project involves the following key steps:

- **Data Cleaning:** Resolving inconsistencies, handling missing values, and correcting anomalies to ensure data accuracy.
- **Data Reformatting:** Aligning the dataset with predefined structural and datatype requirements for seamless database integration.
- **Data Splitting:** Dividing the cleaned data into three distinct CSV files tailored for analytical and storage purposes.

## Deliverables
The final output consists of three well-structured and formatted CSV files, ready for direct import into the bank's PostgreSQL database:


## `client.csv`

| column | data type | description | cleaning requirements |
|--------|-----------|-------------|-----------------------|
| `client_id` | `integer` | Client ID | N/A |
| `age` | `integer` | Client's age in years | N/A |
| `job` | `object` | Client's type of job | Change `"."` to `"_"` |
| `marital` | `object` | Client's marital status | N/A |
| `education` | `object` | Client's level of education | Change `"."` to `"_"` and `"unknown"` to `np.NaN` |
| `credit_default` | `bool` | Whether the client's credit is in default | Convert to `boolean` data type:<br> `1` if `"yes"`, otherwise `0` |
| `mortgage` | `bool` | Whether the client has an existing mortgage (housing loan) | Convert to boolean data type:<br> `1` if `"yes"`, otherwise `0` |

<br>

## `campaign.csv`

| column | data type | description | cleaning requirements |
|--------|-----------|-------------|-----------------------|
| `client_id` | `integer` | Client ID | N/A |
| `number_contacts` | `integer` | Number of contact attempts to the client in the current campaign | N/A |
| `contact_duration` | `integer` | Last contact duration in seconds | N/A |
| `previous_campaign_contacts` | `integer` | Number of contact attempts to the client in the previous campaign | N/A |
| `previous_outcome` | `bool` | Outcome of the previous campaign | Convert to boolean data type:<br> `1` if `"success"`, otherwise `0`. |
| `campaign_outcome` | `bool` | Outcome of the current campaign | Convert to boolean data type:<br> `1` if `"yes"`, otherwise `0`. |
| `last_contact_date` | `datetime` | Last date the client was contacted | Create from a combination of `day`, `month`, and a newly created `year` column (which should have a value of `2022`); <br> **Format =** `"YYYY-MM-DD"` |

<br>

## `economics.csv`

| column | data type | description | cleaning requirements |
|--------|-----------|-------------|-----------------------|
| `client_id` | `integer` | Client ID | N/A |
| `cons_price_idx` | `float` | Consumer price index (monthly indicator) | N/A |
| `euribor_three_months` | `float` | Euro Interbank Offered Rate (euribor) three-month rate (daily indicator) | N/A |

## Impact
This project enables the bank to:

- Improve marketing strategy analysis by ensuring clean and structured data.
- Enhance decision-making processes for future campaigns.
- Establish a scalable and flexible data storage system.

## Results and Discussion

### Achievements
- **Data Integrity:** Rectified inconsistencies and missing values to ensure data accuracy.
- **Standardization:** Unified data formats and types for smooth database integration.
- **Optimized Data Segmentation:** Structured the dataset into three logically grouped files for different analytical needs.

### Key Findings
- **Data Quality Improvements:** Identified and addressed missing values and inconsistencies.
- **Uniform Data Structure:** Standardized categorical and datetime fields for easy database querying.
- **Effective Data Splitting:** Created three datasets to facilitate targeted analysis of customer demographics, campaign performance, and economic factors.

## Challenges and Future Recommendations

### Challenges
- Variability in data quality required a combination of manual and automated cleaning techniques.
- Maintaining relational integrity while splitting datasets required careful planning.

### Future Recommendations
- **Automated Data Pipelines:** Implement automated cleaning scripts for efficiency.
- **Data Governance Policies:** Establish guidelines to improve data collection quality at the source.
- **Advanced Analytics:** Use the cleaned data for predictive modeling and campaign optimization.

## Conclusion
This project significantly improves the bank's ability to manage and analyze marketing campaign data. The cleaned and structured dataset ensures seamless integration with PostgreSQL while enabling more effective marketing strategies. Future efforts should focus on automation and predictive analytics to further enhance decision-making and customer targeting.

## License
This project is licensed under the MIT License.

---

### Contact
For any inquiries or collaboration opportunities, feel free to reach out!

---

