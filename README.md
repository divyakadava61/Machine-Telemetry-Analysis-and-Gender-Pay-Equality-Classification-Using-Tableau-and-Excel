# Machine Telemetry Analysis and Gender Pay Equality Classification Using Tableau and Excel

## Project Overview

This project involved performing a two-part forensic data analysis for a manufacturing company, Daikibo Industrials. First, I analyzed one month of telemetry data from machines across global factory locations to determine which factory and device type experienced the most downtime. Second, I classified employee compensation data by equality score to identify job roles with potential gender pay disparities. The tasks involved data preprocessing, dashboard creation in Tableau, and Excel formula-based classification logic.

## Business Understanding

Daikibo Industrials faced two internal concerns:

1. Operational Downtime: With telemetry data available from their four factories, they wanted to understand where machines were failing most frequently and which device types contributed most to operational inefficiency.

2. Pay Inequality Investigation: Following complaints about gender-based pay inequality, the HR department sought help in evaluating roles and locations with possible bias in salary structure, measured through a pre-processed equality score.

Solving these problems was crucial for improving both equipment efficiency and workplace equity.

## Data Understanding

### Telemetry Dataset (May 2021):
- Format: JSON (unified telemetry messages from 4 factories)

- Locations:

  - Daikibo Factory Meiyo (Tokyo, Japan)

  - Daikibo Factory Seiko (Osaka, Japan)

  - Daikibo Berlin (Berlin, Germany)

  - Daikibo Shenzhen (Shenzhen, China)

- Devices: 9 types per factory, each sending data every 10 minutes

- Metric of Interest: "Unhealthy" status indicating machine failure

### Gender Pay Equality Dataset:
- Format: Excel (3 columns: Factory, Job Role, Equality Score)

- Metric: Equality Score ranging from -100 to +100, where 0 represents ideal equality

## Analysis

### Part 1: Tableau Dashboard (Operational Downtime)

1. Calculated Field: Created a new measure called Unhealthy assigning 10 minutes of downtime to each unhealthy machine status.
2. Visualizations:
   - Sheet 1: Bar chart - Total downtime by factory

   - Sheet 2: Bar chart - Total downtime by device type
3. Interactivity: Configured Sheet 1 as a filter to dynamically update Sheet 2 when a factory is selected.
4. Insights: Factory Seiko showed the highest downtime, with LaserWelder devices being the most problematic.

![Machines_Downtime_by_Factory_Dashboard](https://github.com/user-attachments/assets/7f949534-ab8f-4927-a9e7-1d68373f6373)

Link to access the dashboard:
<a href= "https://public.tableau.com/views/Book1_17489831759250/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link"> Machines Downtime by Factory Dashboard </a>

### Part 2: Excel Classification (Equality Score)

1. Task: Added a fourth column classifying the Equality Score into:

- Fair → ±10

- Unfair → <-10 or >10

- Highly Discriminative → <-20 or >20
2. Excel Formula Used:
  
=IF(ABS([@EqualityScore])<=10, "Fair", IF(ABS([@EqualityScore])<=20, "Unfair", "Highly Discriminative"))

<a href ="https://github.com/divyakadava61/Machine-Telemetry-Analysis-and-Gender-Pay-Equality-Classification-Using-Tableau-and-Excel/blob/main/Task%205%20Equality%20Table.xlsx"> Classified Equality Score Dataset </a>

## Conclusion

### Recommendations:

- Operations: Immediate attention should be given to Daikibo Factory Seiko, particularly to its LaserWelder devices, to reduce machine failures and improve uptime.

- HR & Diversity: The equality classification highlights specific roles and factories requiring further auditing and action to address compensation imbalances.

### Future Enhancements:

- Integrate live data pipelines from telemetry systems into Tableau for real-time monitoring.

- Expand the equality analysis by adding visualizations and incorporating additional demographic data for deeper insights.


