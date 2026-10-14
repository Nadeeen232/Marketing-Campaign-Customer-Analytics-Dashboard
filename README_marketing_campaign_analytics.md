# Marketing Campaign & Customer Analytics Dashboard

A data analytics and business intelligence project that evaluates marketing campaign performance, analyzes customer behavior, and identifies the customer segments most likely to respond to future campaigns.

The project uses **Power BI** to transform customer demographic, income, household, purchasing, product-spending, and campaign-response data into an interactive dashboard with actionable marketing insights.

## Project Overview

The main purpose of this project is to answer two business questions:

1. **Which customer groups respond best to marketing campaigns?**
2. **To what extent did the latest campaign achieve its response target?**

The analysis covers **2,213 customers** and **27 source variables**, including customer demographics, income, household composition, spending behavior, purchase channels, campaign history, complaints, and response to the latest campaign.

## Dashboard Preview

Add a screenshot of the final dashboard to the repository, then update the path below if necessary:

```markdown
![Dashboard Preview](docs/dashboard-preview.png)
```

## Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Customers | 2,213 |
| Total Spend | 1,343,339 |
| Average Spend | 607.02 |
| Median Spend | 397 |
| Campaign Responders | 333 |
| Response Rate | 15.05% |
| Response Target | 12.00% |
| Target Achievement | 125.4% |
| Complaint Rate | 0.90% |
| Median Income | 51,373 |

The campaign achieved **125.4% of its response target**, meaning its actual response rate was **25.4% above the defined target on a relative basis**.

## Project Objectives

- Evaluate the latest campaign response rate against a defined target.
- Identify customer groups with the highest response rates.
- Analyze spending patterns across customer segments.
- Explore the relationship between income and total product spending.
- Compare purchasing behavior across store, web, and catalog channels.
- Translate analytical findings into practical targeting recommendations.
- Build an interactive and consistent Power BI dashboard for business users.

## Data Preparation

The dataset was cleaned and validated before dashboard development.

### Validation and Cleaning

- Checked for blank values and fully duplicated rows.
- Confirmed that customer identifiers were unique.
- Verified numerical data types for income, recency, spending, purchases, campaign flags, complaints, and response.
- Confirmed consistent binary encoding using `0` and `1`.
- Standardized categorical labels used in the dashboard.
- Used distinct customer counts to prevent accidental overcounting.

### Engineered Features

#### Total Spending

`Total_Spent` was calculated as the sum of spending across:

- Wine products
- Fruit products
- Meat products
- Fish products
- Sweet products
- Gold products

#### Spending Segments

Customers were assigned to mutually exclusive quartile-based segments:

| Segment | Total Spending |
|---|---:|
| Low-value | Less than 69 |
| Lower-mid value | 69 to 396 |
| Upper-mid value | 397 to 1,047 |
| High-value | 1,048 or more |

The same four-level spending segment field was used in both dashboard charts and slicers to maintain consistent filtering.

## Dashboard Components

The Power BI dashboard includes:

- KPI cards for customers, average spend, response rate, and target achievement
- Campaign response by spending segment
- Campaign response by education level
- Income versus total-spending scatter plot
- Response rate versus target gauge
- Interactive slicers for spending segment, marital status, and education

## Key Insights

- The latest campaign achieved a **15.05% response rate**, exceeding the **12% target**.
- High-value customers recorded the strongest spending-segment response rate at approximately **30%**.
- Response declined as recency increased:
  - **24.1%** for customers with recency from 0 to 30 days
  - **13.8%** for customers with recency from 31 to 60 days
  - **8.4%** for customers with recency from 61 to 99 days
- Customers with no children at home had an average spend of approximately **1,104** and a response rate of **26.6%**.
- Customers in the PhD education group had the highest education-level response rate at **21.0%**.
- Income and total spending showed a generally positive relationship.
- Previous campaign acceptance had the strongest observed association with the latest response, with a correlation of approximately **0.43**.
- Total spending was positively associated with response, while recency was negatively associated with response.
- Wine generated the highest recorded product spending, followed by meat products.
- Store purchases were the largest purchase-channel total, followed by web and catalog purchases.

> These findings describe associations in the available data and should not be interpreted as proof of causation.

## Business Recommendations

1. **Prioritize recent customers**  
   Focus first on customers whose last purchase occurred within the previous 30 days.

2. **Use value-based targeting**  
   Prioritize high-value customers and consider lower-cost reactivation offers for low-value customers.

3. **Leverage previous campaign acceptance**  
   Build target audiences from customers who accepted earlier campaigns.

4. **Personalize product offers**  
   Use wine and meat purchasing preferences to design relevant bundles and cross-selling offers.

5. **Improve campaign measurement**  
   Capture campaign cost, attributed revenue, channel, campaign date, and control-group information in future campaigns.

6. **Monitor target achievement**  
   Treat 100% as the point at which the response target is met and track performance above or below that benchmark.

## Tools and Technologies

- **Power BI** for data modeling, DAX measures, visualization, and dashboard development
- **Power Query** for data cleaning and transformation
- **Microsoft Excel / CSV** for source-data storage and review

## Repository Structure

```text
.
├── data/                  # Source or cleaned dataset, if redistribution is permitted
├── docs/                  # Dashboard screenshots and supporting documentation
├── dashboard/             # Power BI .pbix file
├── reports/               # Final project report
└── README.md              # Project documentation
```

Update this structure so that it matches the files and folders in the repository.

## How to Use the Project

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/marketing-campaign-analytics-dashboard.git
cd marketing-campaign-analytics-dashboard
```

2. Open the `.pbix` file using **Power BI Desktop**.
3. Update the data-source path if Power BI cannot locate the dataset automatically.
4. Select **Refresh** to load the data.
5. Use the dashboard slicers to explore customer groups and campaign performance.

## Data and Analytical Limitations

- The dataset does not contain campaign cost, attributed revenue, profit, advertising channel, or a control group.
- ROI, ROAS, cost per acquisition, and incremental campaign lift cannot be calculated from the available variables.
- The 12% response target is an analytical management benchmark and is not stored in the original dataset.
- Eight income observations exceed 150,000, including one value of 666,666. These observations were retained but should be reviewed before predictive modeling.
- `Dt_Customer` represents the customer enrollment date rather than the campaign date, so it should not be used as a campaign-performance timeline.
- Results from small customer groups should be interpreted carefully.

## Future Improvements

- Add campaign cost and attributed-revenue data to calculate ROI and ROAS.
- Record campaign channel and campaign launch date.
- Introduce a control group to estimate incremental lift.
- Build a predictive model for campaign response.
- Apply customer-lifetime-value and RFM segmentation.
- Publish the dashboard through Power BI Service, subject to data-privacy requirements.
- Track performance across multiple campaigns and replace the analytical benchmark with an approved business target.

## Acknowledgment

This project was completed as a final data analysis and dashboard project focused on marketing campaign performance and customer analytics.

## License

This repository is intended for educational and portfolio purposes. Add an appropriate license only after confirming that the dataset, dashboard assets, and supporting files can be redistributed.
