# B2B Sales Decision Engine

Business Impact Focused | Production-Oriented Thinking | Decision Intelligence

Executive Summary

This project analyzes sales pipeline data for a B2B SaaS organization experiencing a decline in win rate despite maintaining a healthy pipeline.

The objective is to diagnose the underlying drivers of conversion decline and design a decision intelligence system that enables sales leadership to take proactive, data-driven actions to improve revenue outcomes.

Rather than focusing purely on model accuracy, the project emphasizes business interpretation, operational usability, and decision support — critical characteristics of real-world data products.

Problem Framing
What is the real business problem?

The primary issue is declining deal conversion efficiency rather than insufficient demand.
Despite a seemingly healthy pipeline, fewer opportunities are translating into closed revenue.

This suggests potential breakdowns in:

Pipeline quality

Deal qualification

Sales execution

Segment targeting

Sales leadership currently lacks clear visibility into why deals are being lost and where intervention is required, resulting in reactive decision-making instead of proactive revenue management.

Key Questions the System Must Answer

An effective sales intelligence system should provide clarity on:

Which segments (region, industry, product, deal size) are driving win-rate decline?

Are losses concentrated in specific deal stages?

Is pipeline volume growing while quality deteriorates?

Which active deals resemble historically lost opportunities?

What actionable levers can improve conversion outcomes?

The goal is not reporting — it is enabling better executive decisions.

Metrics That Matter
Core Metrics

Win Rate

Average Deal Size (ACV)

Sales Cycle Length

Pipeline Volume vs. Closed Deals

Win Rate by Segment

Diagnostic Metrics

Pipeline Quality Score
Formula: Won Deals / Late-Stage Deals
→ Evaluates how realistic the pipeline truly is.

Sales Efficiency Index
Formula: Revenue Won / Total Sales Cycle Days
→ Identifies where revenue converts fastest and highlights execution efficiency.

Together, these metrics help distinguish between a pipeline quantity problem and a pipeline quality problem.

Key Assumptions

Deal stages follow a consistent sales process

CRM data accurately reflects timelines and outcomes

Closed deals represent genuine customer decisions

No major pricing or product shifts distort historical patterns

Sales reps operate under broadly comparable conditions

These assumptions are important and should be revisited when deploying the system in production environments.

Data Overview

The dataset represents a structured B2B sales pipeline containing deal-level attributes such as:

Region

Industry

Product Type

Deal Stage

Lead Source

Deal Value

Sales Cycle Duration

Each record captures whether a deal was ultimately won or lost, enabling both diagnostic analytics and predictive modeling.

Exploratory Analysis – Key Findings

Win rates were broadly consistent across regions, suggesting geography is not a primary driver of conversion decline.

FinTech opportunities demonstrated marginally stronger conversion compared to other industries.

Inbound leads converted at a slightly higher rate, indicating stronger purchase intent relative to outbound channels.

These insights suggest that execution and qualification — rather than market location — may be stronger drivers of performance.

Pipeline Diagnostics

Late-stage analysis revealed that only ~47% of deals in Negotiation or Closing stages were ultimately won.

This signals potential pipeline inflation, where deals advance without sufficient qualification, creating overly optimistic revenue expectations.

Improving late-stage rigor could materially enhance forecast reliability.

Decision Engine – Deal Risk Scoring

To move beyond descriptive analytics, a predictive risk model was developed to estimate the probability of deal loss for active opportunities.

The objective is not perfect classification, but directional intelligence that helps leaders prioritize attention where it matters most.

Model Performance

The model achieved ~56% accuracy on the test set.

While performance is intentionally directional rather than deterministic, it provides enough signal to:

Prioritize interventions

Improve pipeline focus

Reduce late-stage surprises

In large sales organizations, even moderate predictive lift can drive meaningful revenue impact.

Key Risk Drivers

Top variables influencing deal outcomes included:

Deal Amount

Sales Cycle Length

Product Tier

Deal Qualification Stage

Partner-led sourcing

Notably, larger deals with extended sales cycles exhibited higher loss probability — highlighting execution risk commonly associated with complex enterprise motions.

Business Impact

The risk scoring engine enables sales leadership to:

Prioritize high-risk deals for early intervention

Allocate experienced reps to complex opportunities

Improve forecast accuracy

Strengthen pipeline hygiene

Reduce unexpected revenue shortfalls

This shifts sales management from intuition-driven oversight to data-informed execution.

Part 4 – Sales Insight & Alert System Design
Objective

The goal is to operationalize the decision engine by building a lightweight system that continuously monitors pipeline health, scores deal risk, and proactively alerts leadership before revenue is impacted.

Rather than relying solely on static dashboards, this approach enables proactive revenue management.

High-Level Architecture

CRM → ETL Pipeline → Feature Store → Risk Model → Insight Engine → Alerts + Dashboard

Core Components

CRM System
Primary source of deal activity and pipeline updates.

Data Pipeline
A scheduled ETL workflow cleans, validates, and standardizes sales data.

Feature Store
Maintains consistent, reusable model features to ensure scoring reliability.

Model Layer
Applies the trained risk model to active deals.

Insight Engine
Evaluates business rules to detect emerging risks and performance shifts.

Alerting Service
Delivers notifications via Slack or Email for rapid response.

Dashboard
Provides leadership with real-time pipeline visibility and trend monitoring.

The architecture prioritizes simplicity, scalability, and low operational overhead.

(Strong recommendation: add a simple architecture diagram here — it dramatically elevates perceived seniority.)

Data Flow

Deal data is extracted from the CRM on a scheduled cadence.

The pipeline cleans and standardizes critical fields such as stage, value, and cycle length.

Active opportunities are scored using the risk model.

Business rules evaluate patterns such as rising late-stage losses or abnormal cycle times.

Insights populate leadership dashboards, while critical risks trigger alerts.

This ensures decision-makers are informed early enough to intervene effectively.

Example Alerts & Insights
Deal-Level Alerts

High-value deals flagged with elevated loss probability

Opportunities stalled beyond the typical sales cycle

Rapid stage progression without proper qualification

Pipeline-Level Alerts

Sudden drop in win rate within a segment

Increase in late-stage deal losses

Over-concentration of forecasted revenue in high-risk deals

These alerts enable targeted action instead of reactive firefighting.

Execution Frequency

Risk Scoring: Daily

Pipeline Health Checks: Daily

Executive Summary Metrics: Weekly

Near real-time infrastructure is intentionally avoided to reduce system complexity while still supporting effective decision-making.

Failure Cases & Limitations

Data Quality Risk: Inaccurate CRM updates can distort model outputs.

Model Drift: Changes in pricing, product strategy, or market conditions may reduce predictive power over time.

False Positives: Some flagged deals will still close successfully.

User Adoption: Alerts must remain actionable to prevent notification fatigue.

Regular monitoring and periodic retraining are recommended to maintain system reliability.

If Productized at Scale

If deployed as an internal product, this system could evolve into a Revenue Intelligence Platform capable of:

Forecasting revenue

Recommending next-best actions for sales reps

Identifying coaching opportunities

Detecting pipeline anomalies

Improving qualification discipline

Over time, this transforms sales from intuition-led execution into a predictable, data-driven growth engine.

Conclusion

This project demonstrates how diagnostic analytics, predictive modeling, and lightweight system design can be combined to improve sales execution.

Rather than optimizing purely for model accuracy, the solution emphasizes interpretability, operational usability, and leadership decision support — key characteristics of production-grade data products.

The approach illustrates how data science can evolve from reporting to measurable revenue impact.

## Tech Stack

- Python (Pandas, NumPy, Scikit-learn)
- Data Visualization: Matplotlib / Seaborn
- Feature Engineering & Predictive Modeling
- Exploratory Data Analysis (EDA)
- Business Metrics Design
- Lightweight System Architecture


## Project Type
End-to-End Decision Intelligence Project combining analytics, predictive modeling, and system design to simulate a production-grade sales intelligence solution.


## Repository Structure

notebooks/        → Exploratory analysis and modeling  
data/             → Sample dataset (if shareable)  
README.md         → Project documentation  

Weakest Assumptions

The solution assumes that historical CRM data is accurate, consistently updated, and reflective of real buyer behavior. In practice, CRM hygiene is often imperfect — deal stages may be updated late, qualification criteria may vary across sales reps, and lost reasons are frequently underreported.

Additionally, the model assumes that past conversion patterns will continue to hold. Any significant change in pricing, product positioning, competitive landscape, or go-to-market strategy could reduce the predictive relevance of historical data.

What Would Break in Real-World Production?

The largest risk is data quality degradation. If sales teams fail to maintain structured and timely updates, model outputs could quickly become unreliable.

Another risk is model drift. As the company scales into new segments or launches new products, the feature relationships influencing win probability may shift, requiring continuous monitoring and retraining.

There is also an operational risk — excessive alerts could create notification fatigue, causing teams to ignore the system entirely. For adoption to succeed, insights must remain precise and actionable.

What Would I Build Next With One Month?

Given additional time, the next priority would be transitioning from risk detection to prescriptive intelligence.

Key enhancements would include:

A revenue forecasting layer to improve executive planning

Next-best-action recommendations for sales reps

Rep-level performance diagnostics to identify coaching opportunities

Pipeline anomaly detection to surface hidden risks earlier

Automated model retraining workflows

Together, these capabilities would evolve the system from a diagnostic tool into a true revenue intelligence platform.

Area of Lowest Confidence

The area of lowest confidence is the model’s predictive strength. With ~56% accuracy, the model provides directional guidance but should not be treated as deterministic.

However, the intent is prioritization rather than perfect prediction. Even moderate signal can meaningfully improve resource allocation in large pipelines.

Before production deployment, I would evaluate additional features such as buyer engagement signals, competitive context, and historical rep performance to strengthen predictive power.

Conclusion

This project demonstrates how diagnostic analytics, predictive modeling, and lightweight system design can be integrated to improve sales execution.

Rather than optimizing purely for model accuracy, the solution emphasizes interpretability, operational usability, and leadership decision support — key characteristics of production-grade data products.

The approach highlights how data science can evolve from retrospective reporting to proactive revenue impact.

now this is fine?

## Executive Summary
This project analyzes sales pipeline data for a B2B SaaS organization experiencing a decline in win rate despite maintaining a healthy pipeline.

The objective is to diagnose the underlying drivers of this decline and design a decision intelligence system that enables sales leadership to take targeted, data-driven actions to improve revenue outcomes.

---

## Problem Framing

### 1. What is the real business problem?

The core business problem is declining deal conversion efficiency rather than lack of demand.  
Although pipeline volume appears healthy, fewer deals are converting into wins, indicating potential issues with pipeline quality, deal execution, or market fit rather than lead generation.

Sales leadership lacks clear visibility into why deals are being lost and where intervention is required to reverse the trend.

---

### 2. Key Questions the System Must Answer

An effective sales intelligence system should answer:

- Which segments (region, industry, product, deal size) are driving the win-rate decline?
- Are losses concentrated in specific deal stages?
- Is pipeline volume increasing while quality deteriorates?
- Which active deals resemble historically lost deals?
- What actionable levers can improve conversion outcomes?

The objective is not just reporting, but enabling decision-making.

---

### 3. Metrics That Matter

**Core Metrics**

- Win Rate  
- Average Deal Size (ACV)  
- Sales Cycle Length  
- Pipeline Volume vs Closed Deals  
- Win Rate by Segment  

**Diagnostic Metrics**

**Pipeline Quality Score**  
Won Deals / Late-Stage Deals  
→ Evaluates how realistic the pipeline is.

**Sales Efficiency Index**  
Revenue Won / Total Sales Cycle Days  
→ Identifies where revenue converts fastest.

These metrics help distinguish between a quantity problem and a quality problem.

---

### 4. Key Assumptions

- Deal stages follow a consistent sales process  
- CRM data accurately reflects outcomes and timelines  
- Closed deals represent true customer decisions  
- No major pricing or product changes skew the analysis  
- Sales reps operate under comparable conditions  

These assumptions will later be revisited when discussing real-world deployment risks.
**
