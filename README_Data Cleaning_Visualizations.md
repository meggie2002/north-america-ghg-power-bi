## Data Cleaning

**Before Cleaning:**  
![Before Cleaning](https://github.com/user-attachments/assets/ea3b7087-a19a-4bb9-8096-0889729b708b)
<br>
28% of null in gdp, 50% of null in coal_co2, 64% of null in gas_co2, 28% of null in co2_per_gdp, 7% of null in primary_energy_consumption, 7% of null in energy_per_capita 

**After Cleaning:**  
![After Cleaning](https://github.com/user-attachments/assets/e649fe28-3b97-4b45-85b9-fcc76e2dc9c4)
➔	GDP <br>
For each country, the median GDP is calculated using the “Group By” feature. This median value will be used to fill missing GDP entries. The summary sheet is then merged back into the original dataset, so that each row has access to its country’s median GDP value. And a new column “GDP_new” is created. If the original GDP is missing, it is replaced with the country’s median GDP; otherwise, the original GDP is retained.<br> 
➔	Co2_per_gdp <br>
Created a new column “co2_per_gdp_NEW”. If the GDP_new is zero, the value is set to 0 otherwise calculated as co2 emissions divided by GDP_new. <br>
➔	coal_co2, gas_co2, primary_energy_consumption, energy_per_capita replaced null values with zero. 
 
**Before Transformation:**  
![Before Transformation](https://github.com/user-attachments/assets/eb24c6fc-4193-43a6-973d-926c60e79080)<br>
➔	Countries with very high emissions (such as, the United States, Canada, and Mexico) dominate the chart, with much taller bars than other countries. <br>
➔	Most other countries appear with very small bars, making it difficult to distinguish differences among them. <br>

**After Transformation:**  
![After Transformation](https://github.com/user-attachments/assets/39d24236-9708-4358-b1cd-bd68f896c28e)<br>
➔	The log transformation compresses the range of values, reducing the visual dominance of the largest emitters. <br>
➔	Differences among countries with lower and mid-range emissions become more visible and comparable. <br>

**Before Negative Transformation:**  
![Before Negative Transformation](https://github.com/user-attachments/assets/ce9e47f3-37c0-441a-9287-c7513bae9776)<br>
Including negative values (carbon sinks) and positive values (carbon sources). <br>
**After Negative Transformation:**  
![After Negative Transformation](https://github.com/user-attachments/assets/8e47eab7-fbf5-4ba3-84f0-b6279323afc1)<br>
The log transformation compresses the range of values, reducing the influence of extreme outliers. Negative values (now shifted and log-transformed) are still present, but their magnitude is visually comparable to positive values.<br> 
**Column Calculations:**  
![Column Calculations](https://github.com/user-attachments/assets/ad9d2be6-c593-4ee5-8316-3e0f3aa86ca9)<br>
➔	In our dataset there are three greenhouse gases CO2, methane, nitrous oxide. <br>
The total_ghg column likely includes these gases and may also incorporate estimates for additional greenhouse gases, but they are not broken out separately. The contribution of these “other” gases is usually small compared to CO2, methane, nitrous oxide, but in some countries or sectors, they can be significant. <br>
➔	Despite this limitation, total_ghg remains suitable for most analyses, as it provides a comprehensive measure of overall greenhouse gas emissions. But it is important to note that the dataset does not include separate reporting for minor greenhouse gases, and users should interpret results with this consideration in mind.<br>

---

## Visualizations and Findings

### 1. How have total and per capita CO₂ emissions changed over time?
![CO₂ Emissions Over Time](https://github.com/user-attachments/assets/69a288d8-1c9d-4ac7-8884-cca7e28debd8)
<br>
There is a gradual increase in total CO₂ emissions from 2000 to around 2010, followed by a slight decline in recent years. Per captia emissions show a similar trend but with less fluctuations. 
### 2. How do GHG emissions correlate with GDP and energy use?
![Emissions, Energy vs GDP](https://github.com/user-attachments/assets/83ea83d6-fa0a-44a4-8b1c-7219f5b57ee6)<br>
➔ There is a strong positive correlation between energy use per capita and GHG emissions per capita. <br>
➔ Trinidad and Tobago (dark green) has very high energy use per person and very high GHG emissions per person, but the size of point is small that indicates low GDP. Unlike Canada, USA which also shows high energy and emissions per capita and has a high GDP. <br>
➔ Some Caribbean nations of North America (Bahamas, Antigua and Barbuda) show high energy use per capita but relatively moderate emissions. 
### 3. Which sectors contribute most to CO₂ emissions?
![Sectoral Contributions](https://github.com/user-attachments/assets/24cc6a68-7d4c-47f9-9550-168f25f84edd)
<br>
➔	United States: Dominated by oil and coal, with substantial contributions from natural gas. <br>
➔	Canada: High emissions from oil and gas, with notable land use change impacts. <br>
➔	Mexico: Oil is the primary source, with moderate coal and gas. <br>
➔	Smaller Nations: Sectoral emissions are much lower but often dominated by a single source.

### 4. Energy use vs. emissions intensity
![Energy Use vs GHG Intensity](https://github.com/user-attachments/assets/e25d27ae-c2e6-4af8-a136-19c43217aa83)<br>
➔ High Energy, Lower Emissions: Some countries (e.g., Bahamas, Barbados) exhibit high energy use but lower emissions intensity. <br>
➔ High Intensity: The United States and Canada are high in both energy use and emissions, indicating a need for cleaner energy sources. Caribbean nations of North America achieve high energy consumption per capita with lower emissions intensity. <br>
➔ Trinidad and Tobago stands out for extremely high primary energy consumption and greenhouse gas emissions per capita-among the highest globally. 
### 5. Methane and N₂O contributions
![Methane   N₂O Contributions](https://github.com/user-attachments/assets/f013fbc8-eda9-4864-ad65-89e1574bbe7c)<br>
➔ United States, Mexico, Canada these countries have the highest total GHG emissions. <br>
➔ CO2 is dominant but methane and nitrous oxide also contribute to US and Mexico. <br>
➔ In Trinidad and Tobago shows a high proportion of CO₂ emissions relative to methane and nitrous oxide and total GHG emissions are high for its size, mainly driven by CO₂. Central American and Caribbean Countries have lower total GHG emissions overall. <br>
➔ The shares of methane and nitrous oxide are relatively more prominent in some countries (Belize, Barbados, Saint Lucia). CO₂ remains the largest contributor in most cases. 

