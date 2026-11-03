---
name: "travel-finder"
description: "Finds the cheapest flight destinations available to depart today or tomorrow from a given home airport, filtering for budget-friendly options. Returns exactly 3 US domestic destinations and 1 worldwide international destination."
---

Cheap Last-Minute Travel Finder

#Objective
Help the user quickly discover the cheapest flight destinations departing immediately (today or tomorrow) based on real-time flight data and user budget constraints. The final selection must strictly consist of **3 US domestic destinations** and **1 worldwide international destination**.

#Step-by-Step Execution Plan

1. **Clarify Missing Parameters**:
   - Confirm the user's origin airport code (default to MSY if unspecified).
   - Confirm the maximum budget limit (default to $300 for US flights, $600 for worldwide, or use user-specified limits).
   - Set the target departure window to today's date (use the current date from context) or tomorrow.

2. **Search Flight Options**:
   - **US Domestic Search:** Search for one-way flights departing from the origin airport to top budget hubs or popular cities across the United States.
   - **Worldwide Search:** Search for one-way international flights departing from the origin airport to global destinations (e.g., Caribbean, Central/South America, or accessible Europe routes).

3. **Filter and Select**:
   - Filter out any flight options exceeding the defined budget thresholds.
   - Select the **top 3 cheapest US domestic destinations**.
   - Select the **cheapest 1 worldwide international destination**.

4. **Format the Output**:
   Read `output-template.md` (in this skill's folder) and present the final results using that exact structure: the report title, the US Domestic table with 3 rows, the Worldwide table with 1 row, and the closing *Recommended Action* line. Replace every bracketed placeholder with real data — city and state/country, airport code, airline, departure date and time, and one-way price. Keep the US rows sorted cheapest first. If fewer flights fit the budget than the template needs, fill what you can and add a short note under the table saying so, rather than inventing results.
