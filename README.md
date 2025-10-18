
<img width="1280" height="720" alt="Fig  2" src="https://github.com/user-attachments/assets/6b7f8e7b-c48a-4e9e-8545-85d8c310f9ef" />


# Exploratory-Data-Analysis-of-Edge-Hill-University-Photovoltaic-System-Historical-Generation-Output

# SUMMARY
The Durning Centre's photovoltaic (PV) system, with a capacity of 39.02 kWh, represents a significant asset in the realm of renewable energy and smart grid applications. The Exploratory Data Analysis (EDA) will be conducted on the historical generation output of this system in a comprehensive approach to understanding its performance characteristics and potential for integration into advanced analytical models. The primary objective of this EDA is to assess the viability of the dataset for use in machine learning and deep learning models aimed at forecasting future energy generation. Such forecasts are crucial for enhancing the efficiency of smart grids, facilitating renewable power system hybridization with others, and optimizing power system maintenance and usage prioritization for an improved overall performance of the system to encourage modern smart grid innovation.

# SYSTEM SIZE AND SPECIFICATION DETAILS
EDA is a foundational step in the data analysis workflow, providing a comprehensive view of the dataset and guiding subsequent analysis and decision-making processes. It helps analysts gain insights, make informed decisions, and uncover valuable information hidden within the data.
The system is a 39.02kWp PV System with installation arrangement of a 33.84kWp roof top system consisting of 144 x 235W Yingli modules at 10 degrees pitch to roof and 5.18kWp facade system consisting of 28 x 185W Solarcentury modules mounted vertically.
Noteworthy, the PV system relative weather parameters data gotten NASA Prediction of Worldwide Energy Resources for the Prediction of Worldwide Energy Resources (POWER) https://power.larc.nasa.gov/data-access-viewer/ for Edge Hill University, Ormskirk on Latitude 53.558622, Longitude -2.875178 are:
	All sky solar irradiance (kW/m2) 
	Temperature in degree
	precipitation in (mm)
	Wind speed at 10 meters in m/s
	Wind direction at 10 meters in degree
The choice of the weather parameters selected thus far in this analysis is as advised by literatures on Photovoltaic System Performance Influencers.

# GETTING SUMMARY STATISTICS FOR THE ENTIRE DATASET
Getting summary statistics for the entire dataset is a fundamental step. It involves calculating and reviewing various statistical measures that summarize the main features of a dataset, usually in a tabular form. This process provides a quick overview of the data, helping to understand its distribution, central tendency, variability, and other key characteristics. Here's what is typically included in summary statistics.

<img width="940" height="326" alt="image" src="https://github.com/user-attachments/assets/c36647cd-389b-4987-9fb2-f74e9ed7c633" />
The dataset contains 49655 rows of element and covers a time stamp from January 2018 to August 2023.

# RENAMING THE COLUMNS TO GIVE CLEARER MEANING OF TERMS

<img width="941" height="391" alt="image" src="https://github.com/user-attachments/assets/49298414-fe3f-42b9-a39e-baca6f3cbb9a" />

# DATA QUALITY CHECK
# Missing Value Point
Next is to check the qualitative attributes of the data set which includes:
•	Check for Missing Values We will first check for any missing values in the dataset.
•	Identify Anomalies/Outliers We will look for any anomalies or outliers in the dataset that could affect the analysis.
•	Validate Data by ensuring that each column has the appropriate data type, especially the date and time columns.
There are no missing values in the dataset. Each column is fully populated. It is worth mentioning that prior data analysis was conducted on Microsoft Excel to eliminate few cases of missing data point as a result of:
1.	Network Glitch during the upload of the data set to the monitoring portal.
2.	Network or Site-Specific Glitches during the download of the weather data.
The few cases of missing data were handled by replacing the missing data point with a similar value for the previous year to avoid biased analysis.
# Anomalies/Outliers
Based on the summary statistics, there don't appear to be significant anomalies or outliers. The maximum and minimum values for each feature seem within reasonable ranges, but a deeper analysis (such as visualizing with box plots) might be needed for a conclusive assessment. 
# Data Types
Date and Time are currently of the object type. These should ideally be converted to a datetime format for easier manipulation and analysis. Other columns like Total Yield[kWh], ALLSKY_SFC_SW_DWN, T2M, PRECTOTCORR, WS10M, and WD10M are of type float64, which is appropriate for numerical data.
Lastly, the Date and Time columns was successfully merged into a single datetime column named 'Date Time', which is now set as the index of the data frame. This format is more suitable for time series analysis.

# VISUAL PRESENTATION OF THE TOTAL OUTPUT GENERATION OF THE DURNING CENTRE PV SYSTEM [KWH]
When plotting the 'Total Yield[kWh]' time series, you are visually representing the data points of your 'Total Yield[kWh]' variable over a specified time. This graphical representation is crucial in time series analysis as it provides insights into various aspects of the data, including trends, patterns, seasonality, and anomalies. Here's what happens and what to look for in such a plot:
-	Time on X-Axis: The X-axis typically represents time. Each data point on the plot corresponds to a specific time interval (e.g., annually as represented).
-	Total Yield on Y-Axis: The Y-axis represents the values of 'Total Yield[kWh]'. These values could represent energy yield, production.
-	Data Points: Each point on the plot represents the value of 'Total Yield[kWh]' at a specific time. These points are plotted chronologically.
-	Line Connecting Points: In a line plot, the data points are usually connected in the order they occur. This line helps in identifying patterns, trends, and fluctuations in the data over time. The visual is a presented:
<img width="924" height="525" alt="image" src="https://github.com/user-attachments/assets/b648bbf9-376c-4063-8cef-87e3967415b1" />

# REGRESSION PLOT FOR THE TIME SERIES OF 'TOTAL YIELD [KWH]
To analyse the relationship between 'Total Yield[kWh]' of the PV system and the other features based on the regression plots, we typically look for the direction and shape of the regression line. We look for:
-	Directly Proportional (Positive Relationship): If the regression line slopes upwards as the feature increases, it indicates a positive relationship. This means as the feature value increases, the 'Total Yield[kWh]' also increases.
-	Inversely Proportional (Negative Relationship): If the regression line slopes downwards, it indicates a negative relationship. This means as the feature value increases, the 'Total Yield[kWh]' decreases.
-	Partially Proportional: If the regression line is more complex (e.g., a cubic shape), the relationship may change at different values of the feature. This can indicate a partially proportional relationship where 'Total Yield[kWh]' may increase with the feature up to a certain point and then decrease, or vice versa.
-	No Clear Relationship: If the data points are very scattered and do not show any clear trend with the regression line, it might indicate that there is no clear relationship, or that other factors are influencing the relationship.

<img width="924" height="903" alt="image" src="https://github.com/user-attachments/assets/ad8d2b3b-3457-472f-b6b6-5bf9f590a491" />

# THE CORRELATION MATRIX
The correlation matrix is to quantitatively analyse the relationships between 'Total Yield[kWh]' and other features. The correlation matrix provides a numeric representation of the relationships, where values close to +1 indicate a strong positive correlation, values close to -1 indicate a strong negative correlation, and values around 0 indicate no linear correlation.

<img width="944" height="766" alt="image" src="https://github.com/user-attachments/assets/206844a3-0f5e-4105-9072-a85e962f38e3" />

Let's interpret each of these coefficients as the relates to the total yield of the PV System:
-	Correlation Coefficient = 1: This is the correlation of 'Total Yield[kWh]' with itself, which is always 1.
-	Correlation Coefficient = 0.77: This indicates a strong positive linear relationship. A feature with this correlation increases, 'Total Yield[kWh]' tends to increase as well. This is a significant correlation, suggesting that the feature is a good predictor of 'Total Yield[kWh]'.
-	Correlation Coefficient = 0.46: This represents a moderate positive linear relationship. As this feature increases, 'Total Yield[kWh]' tends to increase, but not as strongly as the feature with a 0.77 correlation.
-	Correlation Coefficient = -0.13: This is a weak negative linear relationship. As this feature increases, 'Total Yield[kWh]' tends to decrease slightly. However, the correlation is weak, implying that the feature is not a strong predictor of 'Total Yield[kWh]'.
-	Correlation Coefficient = -0.08: This also indicates a weak negative linear relationship, even weaker than the -0.13 correlation. The influence of this feature on 'Total Yield[kWh]' is minimal.
-	Correlation Coefficient = 0.05: This suggests a very weak positive linear relationship, almost negligible. This feature does not significantly affect 'Total Yield[kWh]'.

# ANNUAL GENERATION OUTPUT OF THE PV SYSTEM
Bar plot and a line plot, both showing the total annual generation output for each year. The bar plot provides a clear comparison between years, while the line plot may help in identifying trends over time.

<img width="970" height="424" alt="image" src="https://github.com/user-attachments/assets/df306d0d-a4b4-4f29-a3b0-dc1864fe97a3" />
<img width="968" height="438" alt="image" src="https://github.com/user-attachments/assets/e6156011-ac9e-42fa-8058-cef684591b58" />
Noteworthy, there was dip in 2023 because the data coverage stopped at September 2023.

# PRO-RATA ANALYSIS FOR 2023 WITH BAR PLOT VISUALISATION OF RESULT
Annual Generation Output with Pro-Rata for 2023 (Highlighted) refers to a specific way of presenting and interpreting the data in your plots, taking into account the adjustments made for partial data in 2023. For clarity:
-	Annual Generation Output: This refers to the total energy production or yield (in this case, 'Total Yield[kWh]') of the PV system for each year.
	With Pro-Rata for 2023: Since the data for 2023 is incomplete (covering only part of the year), a pro-rata calculation is applied. This means the data for 2023 is scaled up to estimate what the full year's data would look like, assuming the rate of generation remains consistent throughout the year. This adjustment provides a more accurate comparison with other years where full-year data is available.

<img width="956" height="653" alt="image" src="https://github.com/user-attachments/assets/80e568a9-777c-4bf1-a4f7-fed6f81ac808" />

In the visualizations, the data for 2023 is specifically emphasized or marked differently (e.g., with a different color of light green). This is done to clearly indicate that the data for this year has been adjusted and is different from the straightforward calculations done for other years. So, the phrase as a whole refers to the presentation of annual energy generation data where the 2023 data has been adjusted to account for partial coverage and is visually distinguished in the plots to make this adjustment clear. 

<img width="945" height="560" alt="image" src="https://github.com/user-attachments/assets/de64a915-0b80-41ea-97ba-46542ab4b8d3" />

This approach provides a more accurate and context-aware interpretation of the data, particularly for comparison across different years. For a clearer understanding of the impact of the adjustment the monthly generation of the PV system comparison (2018 – 2023 generation).
A significant jump in the total yield of a photovoltaic (PV) generation grid from 2019 to 2020 can be attributed to a variety of factors, including operational, environmental, and possibly external events that might have impacted the grid's performance. When analysing such a change, especially within the context of the United Kingdom, several key aspects should be considered:
# Operational Factors
•	System Expansion: An increase in yield could result from expanding the PV system's capacity, such as adding more panels or upgrading existing ones to more efficient models.
•	Improved System Efficiency: Technological improvements or maintenance activities might have enhanced the system's efficiency, leading to higher energy output.
•	Grid Connectivity and Storage: Improvements in grid connectivity and energy storage solutions could also allow for better utilization of generated power, reflecting as an increase in net yield.
# Environmental and Weather Factors
•	Solar Irradiance: A significant factor affecting PV system performance is solar irradiance. The year 2020 might have experienced higher than average solar irradiance, possibly due to fewer cloudy days. The record-breaking sunny spring in 2020 would have significantly enhanced solar PV generation, given the direct correlation between sunlight exposure and electricity production.
•	Temperature: PV panels operate more efficiently at cooler temperatures. A cooler year or periods of cooler weather in 2020 could have positively impacted the system's performance. According to the Met Office:
-	Increased Sunshine in 2020: The record-breaking sunny spring in 2020 would have significantly enhanced solar PV generation, given the direct correlation between sunlight exposure and electricity production.
-	    Temperature Effects: While higher temperatures can reduce the efficiency of solar panels, the overall increase in sunshine hours likely compensated for any efficiency losses, resulting in a net increase in solar generation.
-	    Weather Extremes in 2019: The extremes of heat and rainfall in 2019, especially the significant rainfall in June, may have adversely affected solar generation in some periods.
In summary, the exceptional sunny conditions in the spring of 2020, alongside the general trend of increasing temperatures and sunlight hours due to climate change, likely played a significant role in the observed jump in solar generation yield. This comparison underscores the sensitivity of renewable energy sources to changing weather patterns, highlighting the importance of considering these factors in the planning and operation of solar PV systems.
•	Air Quality: The global reduction in pollution levels in 2020, partly due to lockdowns associated with the COVID-19 pandemic, resulted in clearer skies in many regions. Improved air quality can increase solar panel efficiency by allowing more sunlight to reach the panels.
# External Events - COVID-19 Pandemic
The COVID-19 pandemic led to unprecedented global changes, with potential indirect effects on PV generation:
•	Reduced Industrial Activity: The pandemic caused a significant reduction in industrial activity and vehicular traffic, leading to improvements in air quality.
•	Changes in Electricity Consumption Patterns: Lockdowns and increased remote working shifted electricity demand patterns, possibly influencing grid management and the integration of renewable energy sources.
10.4.	Electrical Analysis Factors
•	System Downtime: Reduced or minimal system downtime in 2020, due to better maintenance or fewer technical issues, could lead to higher annual yields.
•	Inverter Efficiency: The efficiency of inverters, which convert DC electricity from solar panels to AC electricity for the grid, could have improved either through upgrades or more optimal operating conditions.
