

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
# Electrical Analysis Factors
•	System Downtime: Reduced or minimal system downtime in 2020, due to better maintenance or fewer technical issues, could lead to higher annual yields.
•	Inverter Efficiency: The efficiency of inverters, which convert DC electricity from solar panels to AC electricity for the grid, could have improved either through upgrades or more optimal operating conditions.

# AVERAGE MONTHLY TOTAL YIELD [KWH] ACROSS DIFFERENT YEARS
Using a line plot this will display the average monthly 'Total Yield [kWh]' across different years, allowing you to observe seasonal trends and compare performance across years.

<img width="970" height="605" alt="image" src="https://github.com/user-attachments/assets/a28a590c-7f89-424e-9791-c007b706ba65" />
Noticeably, 2020 had the peak that occurred in month 5 (May) and the peak month is relative to all other years.

# COMPARATIVE SEASONAL YIELD OF THE PV SYSTEM
"Comparative Seasonal Yield" refers to an analysis where the average energy production or yield of a photovoltaic (PV) system is compared across different seasons (such as Spring, Summer, Autumn, Winter) and possibly across different years. This type of analysis is valuable for understanding how the yield of a PV system varies with seasonal changes, which can be influenced by factors such as solar irradiance, temperature, and weather patterns.

<img width="944" height="564" alt="image" src="https://github.com/user-attachments/assets/d96a7832-c82e-454e-9b2a-dade05e4ba79" />
<img width="936" height="485" alt="image" src="https://github.com/user-attachments/assets/3494ac3a-78ff-4daa-b846-e411426a9225" />

The Comparative Seasonal Yield affects and is relevant to the total yield of a PV system:
	Solar Irradiance Variations: Solar irradiance can vary significantly across seasons. Typically, summer has higher irradiance due to longer daylight hours and a higher position of the sun, leading to higher energy production. Winter, on the other hand, often sees reduced irradiance.
	Temperature Effects: PV panels can be affected by temperature. Extreme temperatures, both hot and cold, can affect the efficiency of solar panels. In some cases, cooler temperatures in spring or autumn might be more favourable for PV efficiency than the hot summer temperatures.
	Weather Patterns: Different seasons might have varying weather patterns like cloud cover, rain, or snow, which can impact solar energy production. For instance, a season with more cloudy days can result in lower yield.
	Planning and Forecasting: Understanding seasonal trends in solar energy production is crucial for energy planning and forecasting. It helps in predicting energy output, planning for energy storage or backup needs, and optimizing the use of the energy produced.
	System Design and Efficiency: Comparative seasonal yield analysis can inform decisions about system design, such as the angle of solar panels, which can be optimized based on seasonal sun positions to maximize energy capture throughout the year.
In my specific context, analysing the 'Comparative Seasonal Yield' means examining how the average total yield of your PV system varies in different seasons and potentially across different years. This analysis will highlight the times of the year when the system is most productive and when it is less productive, providing insights that could guide the management and optimization of the system.

# AUGMENTED DICKEY-FULLER TEST OF THE TOTAL YEILD OF THE PV SYSTEM
The Augmented Dickey-Fuller (ADF) test is conducted primarily to test for stationarity in a time series. A time series is considered stationary if its statistical properties such as mean, variance, and autocorrelation is constant over time. In other words, a stationary time series does not exhibit trends or seasonal patterns and has consistent fluctuations around a constant mean.
	Interpreting the Results
-	ADF Statistic: This is the test statistic. More negative values indicate stronger evidence against the null hypothesis (that the series is non-stationary).
-	P-value: If the p-value is low (commonly below 0.05), it suggests that the series is stationary.
-	Critical Values: These values are used to compare with the ADF statistic at different confidence levels (e.g., 1%, 5%, 10%). If the ADF statistic is less than the critical value, the null hypothesis can be rejected at that confidence level.
The results of the Augmented Dickey-Fuller (ADF) test for my 'Total Yield[kWh]' time series are as follows:
-	ADF Statistic: -11.615160829122424, 
The ADF statistic is -11.615, which is much lower (more negative) than any of the critical values. A more negative ADF statistic provides stronger evidence against the null hypothesis.
-	P-value: 2.4589727795907197e-21
The p-value is approximately 2.46e-21, which is extremely low (practically 0). A low p-value (typically ≤ 0.05) indicates strong evidence against the null hypothesis.
-	Critical Values:  For 1%: -3.43048183691703, For 5%: -2.861598269199506, For 10%:  -2.5668010147695446.
These critical values correspond to the thresholds for the ADF statistic at different confidence levels. The fact that the ADF statistic is lower than all these critical values suggests that the null hypothesis can be rejected at the 1%, 5%, and 10% levels.
Conclusively, given the ADF statistic and the extremely low p-value, you can reject the null hypothesis of non-stationarity with a high degree of confidence. This means the 'Total Yield[kWh]' time series is stationary. In other words, its statistical properties like mean and variance are consistent over time, making it suitable for many types of time series forecasting models that assume stationarity.

# INVESTIGATING CYCLIC BEHAVIOUR OF THE PV SYSTEM OUTPUT
Investigating Cyclic Behaviour can be done using visual Inspection by Looking for patterns that appear at irregular intervals in the time series plot. By conducting Spectral Analysis using methods like the Fourier Transform to identify periodicity in the data and Autocorrelation and Partial Autocorrelation Plots to identify if there is any autocorrelation in the data, which might suggest cyclic behaviour.
-	Autocorrelation and Partial Autocorrelation Plots
Autocorrelation and Partial Autocorrelation are important concepts in time series analysis, particularly in understanding the relationship of a series with its past values. Let's explore each of these and their applicability in your case of analysing 'Total Yield[kWh]' in a PV system.
	Autocorrelation (ACF)
Autocorrelation, also known as serial correlation or lagged correlation, measures the correlation of a time series with its own past values. It quantifies the degree to which current values in the series are influenced by its past values. An autocorrelation plot (ACF plot) displays the autocorrelation of the series with lags of itself. For instance, at lag 1, it correlates values with their immediate previous value, at lag 2 with values two time periods before, and so on. 

<img width="943" height="791" alt="image" src="https://github.com/user-attachments/assets/69cba727-a666-4e6c-8357-13d5b08fe9fb" />

No significant peaks in the ACF plot indicate that the series is influenced by its past values at those lags. A slowly decaying ACF plot suggests a long-memory process or a trend in the data while a sharp drop after a few lags can indicate seasonality.
	Partial Autocorrelation (PACF)
Partial autocorrelation measures the correlation of a series with its past values while controlling for the values at all shorter lags. It isolates the correlation at each lag, removing the effect of previous lags. 

<img width="940" height="758" alt="image" src="https://github.com/user-attachments/assets/b4f98f17-90d8-4bfa-ba7d-fbcc33a01e36" />


No Significant spikes in the PACF plot indicate the number of lags that have a direct relationship with the current value of the series. PACF is particularly useful in identifying the order of autoregressive (AR) terms in ARIMA modeling.
# Applicability in my PV Output Generation Analysis
In the context of analysing 'Total Yield[kWh]' of a PV system, the ACF and PACF plots can help you understand how current energy yields are influenced by past performance. For instance, a strong autocorrelation at certain lags could suggest a pattern or rhythm in the energy production.
Furthermore, it helps to guide model selection for forecasting. The PACF plot can help determine the appropriate number of AR terms to include in the model. It also help in detecting seasonality and trends because significant autocorrelations at specific lags might indicate seasonality, which is crucial for a PV system as energy yield can be season-dependent.
In summary, ACF and PACF analyses can provide deep insights into the temporal structure of your time series data, helping in both understanding past behaviour and forecasting future performance.

# ROLLING MEAN ANALYSIS
The rolling mean (also known as the moving average) is a widely used technique for smoothing time series data to identify trends. It involves calculating the average of the data points within a specified window that 'rolls' or moves across the data. Here's how it helps in identifying trends:
# Smoothing Short-Term Fluctuations
 By averaging the data over a window, the rolling mean smooths out short-term ups and downs. This makes it easier to see long-term movements or trends in the data.
# Indicating Trend Direction:
If the rolling mean is consistently increasing over a period, it indicates an upward trend. The data, on average, is increasing over that period.

<img width="940" height="678" alt="image" src="https://github.com/user-attachments/assets/06f434c9-b48b-4a75-bb37-e8d0c6ccf097" />

In my specific case, examining the rolling mean of 'Total Yield[kWh]' helps in determining whether there's a general upward or downward trend in the energy yield of the PV system over time. This insight can be instrumental in assessing the performance and planning for future adjustments or investments in the system.


# YEAR-OVER-YEAR CHANGE [KWH] IN GENERATION OUTPUT OF THE PV SYSTEM
The Year over Year analysis and percentage change provides insights into the annual performance of your PV system, highlighting any significant increases or decreases in yield over the years. It can be particularly useful for identifying trends and evaluating the impact of any changes or interventions made in the system.

<img width="944" height="381" alt="image" src="https://github.com/user-attachments/assets/e12197d8-a292-44e0-a495-5d362717c93c" />
<img width="903" height="543" alt="image" src="https://github.com/user-attachments/assets/c8ffa994-b217-49c4-8791-0877d9888688" />
From the result we can see that in 2019, 2020 and 2022 year end, there was an increase in the generation output as compared to the big decreasing dip in generation that occurred in 2023.


<img width="941" height="580" alt="image" src="https://github.com/user-attachments/assets/ec096205-ea92-471c-8d07-4cb6aa120dd4" />
These visualizations will allow you to quickly identify years with significant changes in yield, either increases or decreases, and may help in pinpointing any external factors or system changes that might have influenced these variations.

# QUARTERLY GENERATION OF THE PV SYSTEM FOR COMPARISON
The quarterly generation visualisation analysis will help in observing the quarter in the year where the generation is maximum from the PV system. The observation that the second quarter (which typically encompasses April, May, and June) consistently shows higher solar energy generation across all years can be justified from the angle of seasonality, especially in the context of solar energy production. Let's explore the key factors contributing to this pattern:
# Increased Daylight Hours 
The second quarter marks the transition from spring to early summer in the Northern Hemisphere. During this period, the days get progressively longer, resulting in increased daylight hours. More daylight hours directly translate to more sunlight available for solar panels to convert into energy.
# Solar Angle and Intensity
As the sun moves higher in the sky during these months, solar radiation becomes more intense. The angle of the sun’s rays is more direct compared to winter months, leading to more efficient energy generation as solar panels receive more concentrated sunlight.
# Weather Conditions and Temperature Effect
Typically, the second quarter is characterized by clearer skies and less precipitation compared to other times of the year like late autumn or winter. Clear skies mean fewer obstructions for sunlight, maximizing the potential for solar energy generation. Also, while extremely high temperatures can reduce the efficiency of solar panels, the moderate temperatures of late spring and early summer are often ideal for solar energy production. It's often in the peak of summer (usually in the third quarter) that extreme heat might start to negatively impact efficiency.
# Historical Patterns and Predictability
The consistent pattern observed over multiple years suggests a strong seasonal trend. In solar energy production, seasonality is a well-known and predictable factor, and the trends observed in the data align with these broader patterns.

<img width="940" height="909" alt="image" src="https://github.com/user-attachments/assets/1fe7d20b-7f3d-43c4-a417-6d1b15902116" />

# SCATTER PLOTS TO VISUALIZE OUTLIERS IN THE ENTIRE DATASET
<img width="949" height="1121" alt="image" src="https://github.com/user-attachments/assets/bdae4281-b8ea-461f-adfd-52d0f4494b98" />

# Interpreting the Scattered Plot
Looking out for repeating patterns at regular intervals. For example, if a feature shows a consistent rise and fall pattern every year, it might suggest seasonality. Also, points that are significantly distant from others can be potential outliers. These are data points that are unusually high or low compared to the rest of the data. Lastly, is to check if the spread of the data points changes over time. A widening spread suggests increasing variance, while a narrowing one suggests decreasing variance.

# FEATURES IMPORTANCE TEST FOR UNIVARIATE AND MULTIVARIATE MODELING ANALYSIS
The correlation analysis of the features in relation to the 'Total Yield[kWh]' reveals a significant insight: only the first two features exhibit a positive correlation with the target variable. This finding suggests that these two features have a linear relationship with the total yield, where increases in their values are associated with increases in 'Total Yield[kWh]'.

<img width="931" height="565" alt="image" src="https://github.com/user-attachments/assets/35e6a735-cac3-4fef-add2-f6f4d3ed1186" />

In summary, the positive correlation of the first two features with 'Total Yield[kWh]' highlights their potential importance and warrants further investigation, especially in the context of predictive modeling and feature selection. This analysis forms a solid foundation for the next steps in the data science workflow, particularly in the realms of feature engineering and model development.

# IDENTIFYING AND REMOVING THE OUTLIER FROM THE YEAR 2021 IN 'TOTAL YIELD[KWH] OF THE PV SYSTEM
To remove all rows from your Data Frame where the 'Total Yield[kWh]' exceeds 30 kWh. The resulting Data Frame will no longer contain these outliers. The scattered plot visualisation for 2021 generation below is done to check if the cleaned data set is free from outliers in the Total yield of the PV System.
<img width="944" height="540" alt="image" src="https://github.com/user-attachments/assets/06f95038-835f-44e5-8205-529391e9c2eb" />

# IDENTIFYING AND REMOVING THE OUTLIER FROM IN WEATHER PRECIPITATION OF THE PV SYSTEM
Although, the precipitation column did not correlate well with the target variable (the total yield of the PV system) according to the previous analysis carried out, we can still remove the outliers in their data set.

<img width="940" height="516" alt="image" src="https://github.com/user-attachments/assets/f7ad36f5-5c4a-49cc-a3d8-e03e010fb400" />

# CONCLUSION (EXECUTIVE SUMMARY)
The comprehensive Exploratory Data Analysis (EDA) conducted on the Durning Centre's PV system historical generation dataset indicates a high potential for its application in machine learning and deep learning models. Some observations from the EDA process are:


•	The Durning Centre PV system installation size of 39.02 kWh is 10.98 kWh short of the United Kingdom government's minimum approved generation requirement to sell the DC generation output of largely domestic-scale installations of a renewable energy system to the National Grid (Beis.R. et al., 2019). Nonetheless, the output generation is substantial enough for a preliminary forecasting analysis that can guide the behavioural analysis of the future generation output of small or large-scale PV grids.


•	The year-over-year change [kWh] in generation output of the PV system shows that there was a year-end increment in generation output in three (3) out of the five (5) years from 2018 to 2023 considered in the analysis. 2023 had a huge dip in generation, and the pro-rata analysis conducted for that particular year could not make up for the shortfall in generation. This is a point of concern that can significantly affect the impending forecasting analysis.


•	The correlation analysis and feature importance test carried out show that weather features such as temperature, solar irradiance, and wind speed are positively correlated with the target (total yield of the PV system) that we intend to predict. Wind direction and precipitation weather features are negatively correlated with the target variable, making them unsuitable for inclusion as features to avoid affecting the overall accuracy of our prediction.


•	The Augmented Dickey Fuller Test showed that statistical properties like mean, and variance are consistent over time, making the dataset suitable for many types of time series forecasting models that assume stationarity.



•	The seasonality analysis conducted showed that 2021 had the peak generation output of all the years considered, which occurred in the summer. The summer peak generation is relative for the years considered.


In conclusion, the careful preprocessing, along with detailed statistical and visual analyses, has ensured that the dataset is robust, reliable, and primed for predictive modeling. This groundwork paves the way for developing advanced models that can accurately forecast the future energy generation of the PV system. Such forecasts are instrumental in achieving smarter grid integration, optimizing renewable energy use, and prioritizing maintenance and operational decisions, thereby contributing significantly to the efficiency and sustainability of power systems.




# REFERENCES 
• Department of Computer Science and Engineering Department, Edgehill University, UK. 	
Beis.R., Woodman, B., & Connor, P. (2019). Policy and regulatory barriers to local energy markets in Great Britain. EPG working paper: epg 1801. University of Exeter Energy Policy Group.
•	NASA Prediction of Worldwide Energy Resources. Worldwide Energy Resources (POWER) https://power.larc.nasa.gov/data-access-viewer/ for Edge Hill University, Ormskirk on Latitude 53.558622, Longitude -2.875178.
•	https://www.metoffice.gov.uk/about-us/press-office/news/weather-and-climate/2020/2020-round-up
•	https://www.carbonbrief.org/met-office-a-review-of-the-uks-climate-in-2020/
•	https://www.metoffice.gov.uk/about-us/press-office/news/weather-and-climate/2019/weather-overview-2019




