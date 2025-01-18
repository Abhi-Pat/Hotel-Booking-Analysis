# Data Analysis Project

This repository contains a detailed data analysis project that performs data cleaning, analysis, and visualization on a dataset. The project leverages various Python libraries like **Pandas**, **NumPy**, **Seaborn**, **Matplotlib**, and **Plotly** to explore and analyze the dataset. The key analyses involve spatial and descriptive statistics, as well as visualizations to present key findings.

### Key Steps and Analysis

#### 1. **Data Cleaning**
   - Removed invalid entries and records with missing values.
   - Identified and removed duplicate records to ensure data integrity.
   
#### 2. **Descriptive Analysis**
   - Conducted a basic descriptive analysis on the dataset, providing summary statistics and an overview of the dataset’s distribution.

#### 3. **Quantile Extraction**
   - Extracted data in quantile form for further analysis and to identify patterns in the distribution of key variables.

#### 4. **Spatial Analysis: Guest Origins**
   - Performed spatial analysis to understand the geographic distribution of guests by country.
   - Cleaned data further by removing bookings that were cancelled.
   
   **Visualization**: 
   - Converted the cleaned data into a choropleth world map using Plotly to visualize the home countries of guests. This map helps understand the concentration of guests across different regions.
   
   ```python
   map_guest = px.choropleth(data_frame=country_wise_data, 
                              locations=country_wise_data['country'], 
                              color=country_wise_data['No of guests'], 
                              hover_name=country_wise_data['country'], 
                              title="Home country of Guests")
   map_guest.show()
   ```

#### 5. **Analysis of Reserved vs. Assigned Room Types**
   - Analyzed if there is any difference between the reserved and assigned room types.
   - Created a pivot table between the `reserved_room_type` and `assigned_room_type` to find intersections, normalized the data by the index (reserved_room_type), and made the resulting data more readable.

#### 6. **Market Segment Analysis**
   - **6.a. Market Segment Distribution**: Analyzed the distribution of bookings by market segment and visualized the count of bookings in each market segment using a pie chart.
   
   **Visualization**: 
   - Plotted a pie chart to show the market segments and the count of bookings per segment.
   
   - **6.b. Average Price per Night (ADR) Analysis**: Analyzed the Average Daily Rate (ADR) for various room types across market segments.
   - Plotted a bar chart to compare the ADR across market segments, further breaking it down by room type (`reserved_room_type`).

#### 7. **Guest Arrival Patterns**
   - Investigated whether there is a pattern in guest arrivals over time.
   - Created a dictionary `dict_month` to map month names to their respective numeric values.
   - Added a new column `arrival_date_month_index` to convert month names into numeric values, then concatenated columns like `arrival_date_year`, `arrival_date_month_index`, and `arrival_date_day_of_month` to create a combined date column.
   
   - **Analysis**: Analyzed total guests arriving on each day and looked for any patterns in the data. The analysis revealed no significant pattern in guest arrivals over time.

#### 8. **Guest Arrival Distribution**
   - Mapped the distribution of guest arrivals using a combined histogram-line plot, where both the X and Y axes represented guest arrival data.
   - Performed an analysis of the distribution to understand the spread and trends.

   - **Mean and Median Trend Analysis**: Conducted a trend analysis on the mean and median values of guest arrivals and other key variables extracted from the previous charts.

---

### Key Libraries and Packages Used

- **Pandas**: Used for data manipulation, cleaning, and preparation.
- **NumPy**: Used for numerical computations and array handling.
- **Seaborn**: Used for statistical data visualization and generating beautiful plots.
- **Matplotlib**: Used for static, animated, and interactive visualizations.
- **Plotly**: Used for interactive visualizations and mapping. We used Plotly Express for choropleth maps, pie charts, bar charts, and other visualizations.
- **Chart Studio**: A Plotly web service for hosting and sharing graphs.

---

### Files and Structure

- **`data_cleaning.py`**: Contains the data cleaning and preprocessing steps.
- **`analysis.py`**: Includes all the analysis performed on the dataset, including room type comparisons, market segment analysis, guest arrival patterns, and more.
- **`visualizations.py`**: Code to generate all the charts and interactive plots.
- **`data/`**: Contains the raw and cleaned data files used for analysis.
- **`requirements.txt`**: Lists the dependencies required to run the project, including `pandas`, `numpy`, `seaborn`, `matplotlib`, `plotly`, etc.


### Conclusion

This project demonstrates various essential steps in the data analysis workflow, including data cleaning, statistical analysis, and visualization. The use of libraries like Plotly helps create interactive and insightful visualizations, while the analyses provide actionable insights into guest booking behavior, market segment distribution, and guest arrival patterns.

Feel free to explore and extend the project with additional analyses or visualizations based on your needs!
