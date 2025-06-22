# British Airways: Modeling Lounge Eligibility at Heathrow Terminal 3

## Project Overview

This project develops a practical, scalable approach to forecast premium lounge demand at Heathrow Terminal 3 using real British Airways summer schedule data. The method enables efficient planning of lounge space, staffing, and future investment, all while delivering a seamless premium experience for BA’s most valued customers.

---

## Dataset Description

The dataset provides a comprehensive view of all scheduled BA flights departing from Heathrow Terminal 3 during the summer. Each row represents a flight, with these key fields:

- **Flight Information:** `FLIGHT_DATE`, `FLIGHT_TIME`, `AIRLINE_CD`, `FLIGHT_NO`, `DEPARTURE_STATION_CD`, `ARRIVAL_STATION_CD`
- **Route & Region:** `ARRIVAL_COUNTRY`, `ARRIVAL_REGION`, and `Route type` (“Short-haul”, “Long-haul”)
- **Seating Capacity:** `FIRST_CLASS_SEATS`, `BUSINESS_CLASS_SEATS`, `ECONOMY_SEATS`
- **Time of Day:** `TIME_OF_DAY`
- **(If present) Lounge Eligibility:** Estimated numbers for Tier 1, Tier 2, and Tier 3 lounges

This structure allows robust estimation of passenger capacity and lounge eligibility across different route groups.

---

## Process Summary

1. **Grouping Flights:**  
   - Flights were grouped by **Route Type** (Short-haul vs. Long-haul) and **Region** (Europe, North America, Asia, Middle East).
2. **Estimating Passenger Volume:**  
   - Total available seats per group were summed (First, Business, Economy).
3. **Applying Eligibility Assumptions:**  
   - Industry-standard percentages were assigned for lounge eligibility in three tiers, creating a flexible lookup table.
4. **Reusable Tool:**  
   - The resulting table enables British Airways planners to estimate lounge demand for any schedule in seconds.

---

## Key Findings & Visualizations

- **Short-haul Europe** flights have the highest total seat volume, followed by **Long-haul North America**.
- Lounge eligibility percentages are highest for **long-haul routes**, especially North America, reflecting more premium and frequent flyer traffic.
- **Short-haul routes** show lower eligibility, as expected for leisure-heavy, less premium segments.

<p align="center">
  <img src="b6718fa9-6bce-4d97-847a-f673980fef9d.png" width="650" alt="Pivot Table and Bar Chart: Seat Distribution and Lounge Tiers">
</p>
<p align="center"><i>Figure 1: Total Seats by Group and Estimated Lounge Eligibility Percentages</i></p>

---

## Lounge Eligibility Lookup Table

<p align="center">
  <img src="Screenshot 2025-06-22 192348.png" width="700" alt="Lounge Eligibility Lookup Table Example">
</p>

<table>
  <tr>
    <th>Group</th>
    <th>Tier 1 %</th>
    <th>Tier 2 %</th>
    <th>Tier 3 %</th>
    <th>Notes</th>
  </tr>
  <tr>
    <td>Short-haul – Europe</td>
    <td>0.5%</td>
    <td>2.0%</td>
    <td>6.0%</td>
    <td>Leisure/short business routes, fewer premium passengers</td>
  </tr>
  <tr>
    <td>Long-haul – North America</td>
    <td>2.0%</td>
    <td>5.0%</td>
    <td>15.0%</td>
    <td>Highest premium/status volume</td>
  </tr>
  <tr>
    <td>Long-haul – Asia</td>
    <td>2.0%</td>
    <td>4.0%</td>
    <td>12.0%</td>
    <td>Strong premium demand, major business routes</td>
  </tr>
  <tr>
    <td>Long-haul – Middle East</td>
    <td>1.5%</td>
    <td>4.0%</td>
    <td>10.0%</td>
    <td>Steady business/connecting traffic</td>
  </tr>
</table>

---

## Justification & Assumptions

**How did you group the flights?**  
Grouped by Route Type (Short-haul, Long-haul) and Region (Europe, North America, Asia, Middle East) to capture differences in passenger mix and eligibility.

**Why this grouping?**  
These categories are standard in airline planning and best reflect real variations in premium demand.

**What assumptions did you make?**  
Eligibility percentages are based on industry ratios: higher for long-haul/intercontinental, lower for short-haul Europe. They’re simple to update as new data comes in.

**How can your model apply to future schedules?**  
The lookup table is broad-category-based, not flight-specific. Any schedule can be grouped and estimated with the same logic, making it future-proof and scalable.

---

## Conclusion

This approach gives British Airways a **practical, scalable, and transparent** way to forecast lounge demand at Heathrow Terminal 3. Grouping by route type and region—combined with clear eligibility assumptions—lets BA quickly estimate lounge needs for any schedule, supporting smarter space planning, staffing, and future investment to deliver a world-class premium experience.

---

*For more details, see the [Task 1 documentation](Task 1.docx) or review the process and assumptions in the included screenshots and tables.*
