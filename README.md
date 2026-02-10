# B2B Sales Decision Engine

## Executive Summary
This project analyzes sales pipeline data for a B2B SaaS organization experiencing a decline in win rate despite maintaining a healthy pipeline.

The objective is to diagnose the underlying drivers of this decline and design a decision intelligence system that enables sales leadership to take targeted, data-driven actions to improve revenue outcomes.

---

**## Problem Framing

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
