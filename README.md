# AIR-Bnb-Tableau-Project


Today, I propose undertaking another follow-along project in Tableau with Alex the Analyst. Here's the YouTube tutorial link for the Full Beginner Project in Tableau, which will serve as our guide.

https://www.youtube.com/watch?v=zOR0-nygfDE&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=33&ab_channel=AlexTheAnalyst

In this endeavor, we will be working with a Seattle Airbnb dataset sourced from Kaggle. The dataset comprises three separate csv-format files, namely Listings, Reviews, and Calendar. Alex has thoughtfully merged these three datasets into a single comprehensive one, referred to as "combined Airbnb data in 2016." Let me provide you with a concise overview of each table:


Listings: This table encompasses an extensive array of information about each listing, encompassing crucial details like geographical location, property name, property type, number of rooms, fees, availability status, and customer reviews.

Reviews: This table provides a comprehensive compilation of reviews for select listings, featuring attributes such as the review ID, review date, reviewer's identity, and accompanying comments.

Calendar: This table serves as a comprehensive record of the availability status for each listing, offering vital data such as the listing ID, date, and corresponding price for each available slot.

Once the dataset is imported into Tableau Public, our next step is to combine the Listings and Calendar tables together to prepare the final dataset. It's important to note that due to size limitations, Alex opted to join only two tables instead of all three, and we'll follow the same approach.

Here's what we need to do:

Drag the Listings table to the panel and click the down-arrow button, then select "Open."
Also, drag the Calendar table to the panel and perform an inner join between the two tables using the Listing ID as the key (this step is crucial!).

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/79403696-ca92-45ad-a19c-a3bc9dd377a5)

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/a36e6be7-8677-43f3-930e-7844a9106e4a)


Now that we have our final table, let's proceed to worksheet 1 by clicking on the bottom-left tab labeled "Sheet 1." This is where we will begin creating our first visualization!

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/37e3144c-377c-4045-a304-b13a838429f7)


For our initial visualization, we'll create a bar graph to display the prices for each zipcode. This will allow us to identify which geographic locations have higher prices compared to others, giving us insights into potentially more profitable areas for Airbnb hosts.

Here are the steps to build this bar graph:

Drag the variable "Zipcode" to the "Columns" bar and exclude any Null values.
Next, drag the measure value "Price" to the "Rows" section, and select "Average" as the calculated formula for the prices.


![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/a5939d82-c764-444a-9e23-c535a82dd6cd)


![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/a9eb2237-2583-4c78-91b1-83ab000b393f)


Great! Now, to enhance our visualization, let's follow these steps:

Sort the results in descending order based on the average price. This will help us see the most expensive zip codes first.
Add some color to the graph based on the zip codes to make it visually appealing and more informative.
Here's how to do it:

To sort the results in descending order, click on the "Average of Price" label on the "Rows" shelf, then choose "Sort" from the dropdown menu, and select "Descending."
Drag the variable "Zipcode" from the "Data" pane to the "Marks" panel. When you see the triangle dots next to it, change it to "Color" by clicking on the "Color" option (the rectangle with colorful dots).
Update the graph title to "Price By Zipcode."
![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/44609e6e-0db2-4bca-a592-38cd5d92e85b)

For our second visualization, we'll create a map to illustrate the price by zipcode. Let's move to the second sheet in Tableau and follow these steps:

Drag the dimension "Zipcode" to the "Columns" bar.
From the "Show Me" list (located in the top right corner of Tableau), select the "Map" option.
By doing this, Tableau will generate a map that showcases the prices according to different zipcodes. This visualization will provide a spatial representation of how prices vary across different geographic areas. Let's proceed with these steps to create an informative map visualization.

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/7ad61852-6724-4270-a8c5-adb38343d295)

Now, to differentiate the locations on the map using color and labels, follow these steps:

Drag the dimension "Zipcode" from the "Data" pane to the "Marks" panel.
Change the display of "Zipcode" from "Detail" to "Color." This will apply color to each zipcode on the map, distinguishing them from one another.
Similarly, change the display of "Zipcode" from "Detail" to "Label." This will add labels to each zipcode on the map, making it easier to identify them.
By doing this, your map will now be color-coded and labeled, providing a clear visual representation of Airbnb prices in different zipcodes. It will help viewers easily understand the price distribution across various locations. Feel free to proceed and explore the map you've created!

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/da15aedd-9078-4bad-be2e-9ea7997fd814)

In order to know the average airbnb price by location, we can display the price as label as well. Drag the measure “Price” to Marks panel, change the calculated formula to “AVG”, and then display it as “label”. And here’s our second visualization, which correlates with the first bar graph, but just in a more visual way. Now let’s go to the third visualization!


![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/30cc8059-c7af-4a3f-a035-0435104ad629)
o analyze when Airbnb prices hike up and when people spend the most on Airbnb, we can use the "Calendar" table to create a time series graph. Follow these steps to build the graph:

Drag the dimension "Date" from the "Data" pane to the "Columns" bar.
Change the display of "Date" from "Year" to "Week."
By setting the display to "Week," you will be able to visualize the fluctuations in Airbnb prices and spending on a weekly basis, allowing for a more granular analysis of the trends over time. Now, let's proceed to the next step to complete the time series graph.

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/d7260ad2-5178-4647-8178-36ec4bc99b1b)

To remove the data for 2017 and avoid the misleading drop at the end of December 2016, follow these steps to add a filter:

Click the small "down" arrow located next to "WEEK(Date)" on the "Columns" shelf.
Select "Filter" from the dropdown menu.
Drag the date back to 12/31/2016 in the filter dialog box.
By applying this filter, the time series graph will only display data up to December 31, 2016, and exclude the data for 2017, making the visualization more accurate and reflective of the actual trends. Now, the graph will showcase the fluctuations in Airbnb prices and spending up to the end of 2016.

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/415fa1b6-2f16-4eec-9d29-cebb8b1ae383)

To showcase the minimum and maximum revenue by each week in 2016, follow these steps:

Drag the measure "Price" from the "Data" pane to the "Marks" panel.
Change the display of "Price" to "Label."
Click the "Label" box on the "Marks" card.
Select "Min/Max" from the "Marks to Label" section.
By doing this, your time series graph will now display labels for both the minimum and maximum revenue for each week in 2016. This will provide valuable insights into the price fluctuations and help you understand the variations in revenue throughout the year. 

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/fd24f0c8-9b2b-425a-bd20-9afa3c3d0ab9)

The insights about Airbnb revenue reaching its peak at the end of 2016 due to the holiday season are indeed valuable.

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/5af7b33b-8de7-4dfa-8571-8d2001a921e1)
Until now, we've examined Airbnb prices across various locations and analyzed its revenue throughout the year. Now, let's explore the price differences based on the number of rooms in different Airbnb listings. To achieve this, we'll create a graph with the number of bedrooms as columns and the average price as rows.

Follow these steps to set up the visualization:

As "bedroom" is currently a measured value, we need to convert it to a "Dimension" first.
Drag the new variable (now a dimension) to the "Columns" bar.
Next, drag the "Price" value to the "Rows" bar and change the formula from "SUM" to "AVG."
By doing this, your graph will display the average price for each category of the number of bedrooms, providing insights into how the pricing varies based on the size of the accommodation. This visualization will help you understand the pricing trends with respect to the number of rooms in the Airbnb listings. Let's proceed to create this visualization!

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/392383c4-2773-4bf9-8ff7-c657f3ad7d9f)


Furthermore, we have incorporated labels to depict the prices for Airbnb listings with varying numbers of rooms. The visualization clearly shows a positive correlation between the number of rooms and the Airbnb price, indicating that properties with more rooms tend to have higher prices.

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/ea995c0d-38f5-4d4c-93a0-246fdfe8caad)

For our final visualization, we'll create a simple table that counts the number of listings for each type of Airbnb. Follow these steps:

Drag the dimension "Bedrooms" to the "Rows" bar.
Place the "Id" variable in the "Marks" panel.
Change the display of "Id" from "Detail" to "Text."
Switch the formula for "Id" to "Count (Distinct)" since we aim to determine the number of listings for each type of Airbnb.
By doing this, your table will showcase the count of listings for each specific type of Airbnb based on the number of bedrooms they offer. This straightforward visualization will give you a quick overview of the distribution of listings across different accommodation types. Let's proceed to create this table and conclude our set of visualizations!

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/bafc58d8-23e2-43b9-9762-029242778968)

Here's our completed table, displaying the count of listings based on the number of bedrooms. It's evident that as the number of bedrooms increases, the availability of listings decreases. On the other hand, there is a plethora of options available if we are specifically looking for one-bedroom accommodations.



![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/466bb076-c6dc-494f-b117-cb48f9f3147b)



Absolutely! Creating a dashboard in Tableau is an exciting way to bring all the visualizations together and present a comprehensive view of the insights. To create the dashboard:

Click on each sheet (worksheet) tab and drag them to the dashboard panel.
Arrange the sheets in the dashboard in the order you prefer. You can resize and position them as per your layout choice.
Customize the dashboard by adding a title and any relevant annotations.
Once you're satisfied with the layout, you can save the dashboard, and if you wish to share it publicly, you can publish it to Tableau Public.
Tableau Public allows you to share your interactive dashboards with others, making it a great platform for data visualization and exploration. With the insights presented in the dashboard, viewers can gain a better understanding of the Airbnb data and its various trends. Have fun creating your dashboard and sharing your visualizations with others!

![image](https://github.com/Nidhiwa/AIR-Bnb-Tableau-Project/assets/88158951/aaf59bf5-85a4-4681-9f04-c5e84635aac8)


