<h1>British Airways: Modeling Lounge Eligibility at Heathrow Terminal 3</h1>

<p>
  <strong>Project Overview:</strong><br>
  This project provides a flexible, data-driven model for forecasting premium lounge demand at Heathrow Terminal 3. Using real British Airways flight schedule data, the approach helps BA optimize lounge space planning, staffing, and future investments.
</p>

<hr>

<h2>Dataset Description</h2>
<p>
  The <strong>British Airways Summer Schedule dataset</strong> includes every BA flight departing Heathrow Terminal 3 for the summer period.
  <ul>
    <li><b>Flight Information:</b> <code>FLIGHT_DATE</code>, <code>FLIGHT_TIME</code>, <code>AIRLINE_CD</code>, <code>FLIGHT_NO</code>, <code>DEPARTURE_STATION_CD</code>, <code>ARRIVAL_STATION_CD</code></li>
    <li><b>Route & Region:</b> <code>ARRIVAL_COUNTRY</code>, <code>ARRIVAL_REGION</code>, <code>Route type</code> ("Short-haul", "Long-haul")</li>
    <li><b>Seating Capacity:</b> <code>FIRST_CLASS_SEATS</code>, <code>BUSINESS_CLASS_SEATS</code>, <code>ECONOMY_SEATS</code></li>
    <li><b>Time of Day:</b> <code>TIME_OF_DAY</code> (morning, afternoon, evening, etc.)</li>
  </ul>
  This structure enables analysis of passenger volumes and groupings by region and route type to estimate lounge eligibility.
</p>

<hr>

<h2>Process Summary</h2>
<ol>
  <li>Grouped flights using two scalable criteria: <strong>Route type</strong> (Short-haul/Long-haul) and <strong>Region</strong> (Europe, North America, Asia, Middle East).</li>
  <li>Summed total seat counts for each group to estimate passenger volume.</li>
  <li>Applied industry-based percentage assumptions for lounge eligibility in three tiers (Tier 1, Tier 2, Tier 3).</li>
  <li>Created a reusable lookup table, enabling planners to estimate future lounge demand for any schedule.</li>
</ol>

<hr>

<h2>Key Findings & Visualizations</h2>

<ul>
  <li><b>Short-haul Europe</b> has the highest total seat volume, followed by <b>Long-haul North America</b>.</li>
  <li>Lounge eligibility percentages are highest for long-haul routes, especially to North America, reflecting more premium and frequent flyer traffic.</li>
  <li>Short-haul routes show lower eligibility, matching expectations for more leisure travel and fewer premium seats.</li>
</ul>

<!-- Example Chart Embed (replace src with your image file) -->
<p align="center">
  <img Screenshot 2025-06-22 194037="images/lounge_seat_distribution.png" alt="Seat Distribution by Group" width="600"><br>
  <i>Figure 1: Total Seats by Group and Estimated Lounge Eligibility Percentages</i>
</p>

<!-- Example: Add more visuals if needed -->
<!--
<p align="center">
  <img src="images/lookup_table_example.png" alt="Lounge Eligibility Lookup Table" width="500">
</p>
-->

<hr>

<h2>Lounge Eligibility Lookup Table</h2>
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
    <td>Reflects low premium traffic on intra-European routes.</td>
  </tr>
  <tr>
    <td>Long-haul – North America</td>
    <td>2.0%</td>
    <td>5.0%</td>
    <td>15.0%</td>
    <td>Highest premium and status passenger volume.</td>
  </tr>
  <tr>
    <td>Long-haul – Asia</td>
    <td>2.0%</td>
    <td>4.0%</td>
    <td>12.0%</td>
    <td>Strong premium demand, especially on business routes.</td>
  </tr>
  <tr>
    <td>Long-haul – Middle East</td>
    <td>1.5%</td>
    <td>4.0%</td>
    <td>10.0%</td>
    <td>Steady business/connecting traffic; Tier 1 hypothetical.</td>
  </tr>
</table>

<hr>

<h2>Justification & Assumptions</h2>
<ul>
  <li><b>Grouping:</b> By route type and region to capture real differences in passenger mix.</li>
  <li><b>Assumptions:</b> Eligibility percentages are based on typical industry ratios and can be adjusted as new data becomes available.</li>
  <li><b>Reusability:</b> The lookup table applies to any future schedule; planners only need to assign flights to a group.</li>
  <li><b>Tier 1:</b> Percentages included to inform future potential for a premium lounge (e.g., Concorde Room) even if not currently available.</li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>
  This modeling approach enables British Airways to forecast lounge demand quickly and accurately, supporting smarter planning for premium customer experience. The process is transparent, scalable, and adaptable to future changes in flight schedules or customer behavior.
</p>

---

