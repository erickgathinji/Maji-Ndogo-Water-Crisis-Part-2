
## Maji Ndogo Water Accessibility and Infrastructure Analysis

This project delves into a comprehensive dataset to uncover the underlying issues contributing to Maji Ndogo's water crisis, transforming raw data into actionable insights and a strategic plan for intervention.

---

### Introduction

The mission of this project is to thoroughly analyze a reservoir of data concerning water access in Maji Ndogo. Moving beyond isolated data points, the goal is to discern larger patterns and trends, clustering data to gain a panoramic understanding and unearth broader narratives and hidden correlations within the rich dataset. The survey aimed to **identify water sources**, **determine total and average users** for each source, and **examine the duration citizens typically spend in queues** to access water. This effort is crucial for uncovering solutions to Maji Ndogo's water crisis.

---

### Context: The Maji Ndogo Water Crisis

President Aziza Naledi emphasized the importance of data-driven solutions. Initial data inconsistencies were identified by Chidi Kunto, prompting the decision to bring in an independent auditor to ensure accuracy and trust in the data. The insights gained from this analysis will be used to formulate a plan to restore water access.

---

### Data Overview

The analysis utilized several tables within the `md_water_services` database, including:
*   `auditor_report`
*   `combined_analysis_table`
*   `data_dictionary`
*   `employee`
*   `global_water_access`
*   `incorrect_records`
*   `location`
*   `project_progress`
*   `visits`
*   `water_quality`
*   `water_source`
*   `well_pollution`

**Key Data Points:**
*   **Total People Surveyed:** Approximately **27.6 million citizens** were surveyed.
*   **Survey Duration:** The data collection spanned **924 days**, roughly 2.5 years. This highlights the extensive effort involved in gathering the data.
*   **Location Distribution:**
    *   The entire country was properly surveyed, ensuring the dataset accurately represents the on-the-ground situation.
    *   **60% of all water sources are located in rural communities**, while 40% are in urban areas. This geographic distribution is a critical factor for decision-making.
    *   Provinces like Kilimani (9510 records), Akatsi (8940), Sokoto (8220), Amanzi (6950), and Hawassa (6030) are well-represented in the survey.

---

### Key Findings & Insights

The analysis revealed critical insights into water access and infrastructure:

#### Water Source Analysis:
*   **Shared Taps:**
    *   **43% of the population relies on shared taps**.
    *   On average, **around 2,000 people share one shared tap**, leading to significant demand.
    *   There are 5,767 shared tap sources recorded.
*   **Wells:**
    *   **18% of the population uses wells**.
    *   Only **28% of these wells are clean**, indicating widespread contamination.
    *   There are 17,383 well sources recorded, with an average of 279 people served per well.
*   **Tap in Home (Functional & Broken):**
    *   **31% of the population has water infrastructure installed in their homes** (combining `tap_in_home` and `tap_in_home_broken`).
    *   However, **45% of this in-home infrastructure is non-functional** (equivalent to 14% of the total population) due to issues with pipes, pumps, and reservoirs.
    *   There are 7,265 functional `tap_in_home` sources and 5,856 `tap_in_home_broken` sources.
    *   An average of 644 people are served by a functional `tap_in_home` (though realistically this represents ~100 taps for households where 6 people share one tap) and 649 people by a `tap_in_home_broken` source.
*   **Rivers:**
    *   **9% of the population uses rivers** as a water source.
    *   There are 3,379 river sources recorded, serving an average of 699 people per source.

#### Queue Time Analysis:
*   **Average Wait Time:** Citizens face **long wait times for water, averaging more than 120 minutes (123 minutes)**. This means people often spend two hours fetching water if they don't have a tap at home.
*   **Daily Patterns:**
    *   **Saturdays have the longest queue times**, averaging 246 minutes. This suggests people might be collecting water for the week's supply.
    *   **Mondays also experience very long queues**, especially in the morning and evening, as people rush to get water.
    *   **Wednesdays and Sundays have the shortest queues**, averaging 97 and 82 minutes respectively. Sundays are shorter due to cultural priorities for family and religion.
*   **Hourly Patterns:**
    *   Queues are generally **longer in the mornings (06:00-08:00)** and **evenings (17:00-19:00)**, peaking around 19:00 (168 minutes) and 06:00-08:00 (149 minutes). This indicates people collect water before and after work.
    *   On Saturdays, queue times are consistently high, peaking at 282 minutes at 19:00.

---

### Proposed Action Plan

The strategy for addressing the water crisis is data-driven, prioritizing interventions that will benefit the largest number of people:

1.  **Prioritize Impact:** Focus efforts on improving water sources that affect the most people.
    *   **Shared taps** should be improved first, as they serve the largest population.
    *   **Contaminated wells** are a significant concern; fixing them will benefit many.
    *   **Repairing existing broken infrastructure** (e.g., in-home taps) is crucial, as it can simultaneously restore water access for many and reduce queue times for others.
    *   **Installing new taps in homes** is a resource-intensive solution and will be considered a long-term goal, especially for areas with already low queue times.
2.  **Acknowledge Rural Challenges:** Recognize that **60% of water sources are in rural areas**. This implies logistical challenges for repairs and upgrades due to potential issues with road conditions, supply chains, and labor availability.

---

### Practical Solutions

Based on the insights, specific practical solutions are proposed:

1.  **For River Users:**
    *   **Short-term:** Dispatch **water trucks** to provide temporary water in affected regions.
    *   **Long-term:** Send crews to **drill for wells** to establish more permanent water sources.
2.  **For Wells (Contaminated):**
    *   **Immediate:** Install **filters** to purify water. **UV filters** for biological contamination and **reverse osmosis filters** for other pollutants.
    *   **Long-term:** Investigate the underlying causes of well pollution to implement sustainable solutions.
3.  **For Shared Taps:**
    *   **Short-term:** Dispatch **additional water tankers** to the busiest shared taps during peak hours and busiest days (as identified by the queue time analysis pivot table).
    *   **Long-term:** Start work on **installing extra shared taps** where needed, aiming to reduce queue times below the **UN standard of 30 minutes**.
4.  **For Broken In-Home Infrastructure (`tap_in_home_broken`):**
    *   Address broken infrastructure that serves multiple taps (e.g., reservoirs, main pipes). Fixing a single facility can benefit many people, making it a high-impact, albeit expensive, intervention. Further analysis is needed to identify commonly affected areas.
5.  **Taps in Homes (Long-Term):** For shared taps with already short queue times (< 30 minutes), installing taps in homes remains the most effective, but resource-intensive, long-term solution.

---

### Technical Skills Utilized

This project heavily relied on **SQL** for data manipulation, analysis, and transformation. Key SQL skills employed include:

*   **Database Exploration:** `SHOW TABLES` and `SELECT * FROM data_dictionary` to understand database schema and table contents.
*   **Data Cleaning and Transformation:**
    *   **String Functions:** `REPLACE()`, `LOWER()`, `CONCAT()` for updating employee email addresses.
    *   **String Manipulation:** `TRIM()` for removing leading/trailing spaces from phone numbers.
    *   `LENGTH()` to verify string lengths.
*   **Data Aggregation:**
    *   `COUNT()` to count records per town, province, location type, and water source type.
    *   `SUM()` to calculate total people served by water source types and the overall surveyed population.
    *   `AVG()` for calculating average people served by water sources and average queue times.
    *   `GROUP BY` and `ORDER BY` clauses for structured aggregation and presentation.
*   **Date and Time Functions:**
    *   `MIN()`, `MAX()`, `TIMESTAMPDIFF()` to determine survey duration.
    *   `DAYNAME()`, `HOUR()`, `TIME()`, `TIME_FORMAT()` for analyzing queue times by day of the week and hour of the day.
*   **Control Flow:**
    *   `NULLIF()` to exclude zero queue times from average calculations.
    *   `CASE WHEN THEN ELSE END` statements to build a **pivot table** for detailed hourly queue time analysis across days of the week.
*   **Window Functions:**
    *   `RANK() OVER`, `DENSE_RANK() OVER`, and `ROW_NUMBER() OVER` with `PARTITION BY` and `ORDER BY` to assign priority ranks to water sources based on the number of people served, aiding in repair planning.
*   **Mathematical Operations:** Calculating percentages with `ROUND()` for better interpretability.
*   **Data Interpretation and Storytelling:** Translating raw data and query results into meaningful insights and a coherent narrative for stakeholders.

---
