# Visualizations
Dashboard Design Rationale — Telecom Customer Churn Analysis
Screenshot of the dashboard:
 
Objective
The dashboard was built to let a viewer explore which customer characteristics are associated with churn at a glance and help make data driven decisions on retention periodically. The dashboard is designed to be easily perused by various teams during their strategy and monthly KPI discussions and analysis. 
The design follows a top-down structure: title, filters, topline metrics, a top row of diagnostic charts led by the strongest driver, followed by supporting detail and summary tables.
Structure and layout choices
The filter panel (Age Group, Tenure Cohort, Gender, Contract Type, Internet Service, Tech Support Availability, Churn status) sits directly under the title so a user can narrow the whole page to a segment of interest in one place. All charts share these slicers and cross-filter natively in Power BI, so clicking any data point filters every other visual on the page to that selection. 
The top row of cards (customer count, churn count, churn rate, tenure, monthly charges, and the three LTV measures) gives a fixed reference point and at a glance view of all the top line metrics. 
Interactions:
Churn rate and Potential Lost LTV are highlighted in its own card because, of all the top-line numbers, Potential Lost LTV is the one that translates churn into a dollar figure a business stakeholder would act on first and Churn rate allows the user to stay focussed on the key metric for this dashboard.
•	When the Potential lost LTV is greater than the Active LTV it turns red and if it is less than active LTV it turns green. 
•	Similarly, the churn rate is shown in a gradient of green-yellow-red colors for 0%-50%-100%.
Chart-level choices:
The Churn % by Contract Type and Tech Support Availability chart is placed first in the visual hierarchy, top-left, because it carries the dashboard's single strongest finding and should be the first thing a viewer's eye reaches, before they start filtering.
Placing tech-support bars directly against no-support bars within each contract type makes the comparison immediate: month-to-month churn is structurally high (100%) regardless of support, while annual contracts respond strongly to it, dropping to 52.98% and 57.8% with support.
Donut charts (Male/Female churn split) communicate a single two-part ratio per gender and placing them side by side makes the gender comparison immediate.
Potential Churn LTV and Active LTV (stacked bar) was kept as the single view of value at risk.
Avg Monthly Charges by Tenure (line chart) was added to move the dashboard from describing who churns to suggesting why. Tracking monthly charges across tenure bands for churned versus active customers tests whether price is a factor. In this case it is, as one can see the average monthly charges for active customers is much less at $62 as compared to the churned customers at $75 and the same trend extends across all the tenure cohorts.
Churn % by Internet Service (combo chart) pairs churn rate (bar, primary axis) with Potential Lost LTV (line, secondary axis with callout labels) so a viewer can see whether a segment's churn rate and its dollar exposure move together or diverge. A high churn rate in a low-value segment matters less than a lower churn rate in a high-value one. In this case as you can see that the users with Fiber Optic Service are high-value customer with a lower churn rate and hence worth investing into. 
Age Group × Tenure Cohort heatmap was chosen over a stacked bar because it's a genuinely two-dimensional relationship, and conditional-formatted cell shading makes concentration visible without requiring the reader to compare bar lengths across two axes at once. This view is scoped to churned customers specifically, to show where churn concentrates by age and tenure rather than where the base population sits.
Total Customers by Tenure Cohort and Churn (Area Chart) shows whether churn concentrates at a particular tenure stage or is spread evenly, which the flat, elevated pattern across cohorts here suggests is closer to the latter.
Interactions:
All of these charts are interactive to each other so clicking on one bar or data point will filter all the other charts. 
LTV methodology
Active LTV is calculated as tenure multiplied by monthly charges, summed across active customers. 
Active LTV = Tenure * Monthly Charges
Potential Churn LTV applies the average tenure of the active base to monthly charges, as an estimate of what a churned customer might have been worth had they stayed as long as a typical active customer. 
Potential Churn LTV = Average Active Tenure * Monthly Charges
Potential Lost LTV is the difference between that estimate and the actual total charges billed to churned customers before they left, representing the revenue gap attributable to early churn.
Potential Lost LTV = Potential Churn LTV – Sum of Total Charges for Churn
Limitations and next steps
As next steps, I would 
•	extend the price-sensitivity view added in this version (Avg Monthly Charges by Tenure) into a direct churn-rate-by-charge-band chart, to quantify the price effect rather than only visualize it. 
•	add a single summary callout stating the top driver (Contract type and Tech Support) so a first-time viewer reaches the main conclusion before exploring the filters
•	assuming we could gather further information on customer details and month level details, we could add predictive elements and show who are the potential churners and flag to take action on them. 
