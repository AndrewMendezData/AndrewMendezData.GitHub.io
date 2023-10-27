# Flotation Plant Exploration
## A Python Playground

<img src="images/zpythonplayground.png?raw=true">

This is the 4th Project that I posted working through the Data Analytics Accelerator Bootcamp led by Avery Smith. I was introduced to Python and its incredible power!<br>

---

This project is a little different compared to the first three I wrote from this bootcamp. My intention for this project was for it to be a more "skill share" format where I'm describing what I've learned and when, or how, to use specific functions when manipulating and diving into the data. I used a real dataset that came from a Flotation Plant from March to September 2017. (You can access the dataset [here](https://www.kaggle.com/datasets/edumagalhaes/quality-prediction-in-a-mining-process))<br>


### Installing IDE's
I was very interested to learn about IDE's (Integrated Development Environments). These libraries are one of the key reasons by Python is such an incredibly powerful platform for data analysis.<br><br>

My first step in this Python Playground was to install these IDE's using !pip install. I used Pandas (data manipulation), Seaborn (data viz) & Matplotlib (data viz).<br><br>

<img src="images/python1ide.png?raw=true"><br><br>


### Uploading Database Into Deepnote
Next, I uploaded the Flotation Plant data into Deepnote, and then introduced it into my Deepnote notebook.<br><br>

<img src="images/python2csv.png?raw=true"><br><br>

In this code, I am naming a variable "df" (dataframe) to be the CSV file I uploaded containing the data. I'm telling Python that I'm using the Pandas function to read the CSV file: pd.read_csv() and then including the decimal command to replace the commas in the file with decimals to ease of reading.<br><br>


### Getting to Know This Dataframe
One of the important first steps that Data Analysts should NEVER skip is to **get to know** the data that you are working with! In other words, what does each series represent (the columns in Pandas), what's the shape of the dataframe you're working with, are there any NULL variables present, how are the series formatted, is there any missing or incomplete data, what is the range of the data, etc.<br><br>

First, I used the **head** function to get a preview of the first 5 rows of data in the dataframe (first five rows is the default when no parameter is set within the parenthesis in this function).<br><br>

<img src="images/python3head.png?raw=true"><br><br>

I also want to point out here that Python is based on a "Zero Index" where zero represents the FIRST value, which is why in the above graphic we see that the first row has an index of "0". This is also important to remember when using **.iloc**, for example, which we'll visit later on.<br><br>


### Shape of the Dataframe
Next I wanted to know the overall **shape** of the data I was working with, so I used the shape function:<br><br>

<img src="images/python4shape.png?raw=true"><br><br>

Here Python returns these two values encased in paranthesis and separated by a comma. The first value in this set is the total number of rows (737,453) and the second number is the total number of series (24) in the dataframe. This format, (rows, series), is important to understand as well as it applies to other functions as well. <br><br>


### List of Series
Let's take a look at a list of all the series in our dataframe:<br><br>

<img src="images/python5columns.png?raw=true"><br><br>

Python returns a list of all the series present. The list here is represented by the data encased within square brackets INSIDE of the parentheses, and all the data separated by commas and single quotations. <br><br>

Next, let's take a look at a **single series**. Python gives us an overview of the series specified, in this case the "date" column:<br><br>

<img src="images/python6datecolumn.png?raw=true"><br><br>

It returns the first five and last five rows, and gives us the Name, Length, and datatype. Note, here, that the length that Python returned was 737, 453, which matches the total number of rows returned when we used the shape function. But on the left column, the last row comes up as 737, 452! This is the result of the "Zero Index" functionality: the first row here is indexed as "0", therefore the length is accurate even though the index is not the same.<br><br>


### Using describe()
<img src="images/python12describe.png?raw=true"><br><br>

This function returns a count, mean, standard deviation, min, max, and the quartile values of each series. This is an extremely useful function that can further help you get a more bird's-eye-view of your data.<br><br>


### The Timeframe
Another important parameter to be considered is the dates in which the data occurred. We'll use a simple "min" and "max" function to determine the timeframe we're exploring with this data:<br><br>

<img src="images/python13datecleanminmax.png?raw=true"><br><br>

In this code, I'm naming a variable for each value and naming it as the "min" and "max" value of the series "date_clean" and asking Python to print it using text and the variable in a string. Thus, returning the "min" and "max" dates in two sentences.<br><br>


### Data Manipulation
When we are looking at data in Python, we will need to be able to select SPECIFIC data in order to answer business related questions and to add value to the business. <br><br>

An important function to know to do this in Python is the Index Location function:<br><br>

<img src="images/python7iloc.png?raw=true"><br><br>

Here, I am telling Python that I want it to return rows 1-2 which is represented as 0:2 on the left side of the comma. The colon here represents "in between", Python will return the first and second row, but not the third (index 2). The same applies for the series 0:2 which returns the first two columns.<br><br>

If you wanted to specify the first two rows, but ALL of the columns in the dataframe, you would add a colon ":" to the right side of the comma.<br><br>

Further specifying specific rows and series would be encased within square brackets signaling to Python that there is a list.<br><br>


### Discovering the Data Types
Data types are important when manipulating data because you want to make sure that the platform you're using is treating the data appropriately so that your insights are accurate and for your visualizations to populate smoothly.<br><br>

I used the type() function:<br><br>

<img src="images/python8datatypeprint.png?raw=true"><br><br>

Here, we're asking Python to print three things: the first is the datatype of "df" which is our dataframe, the second is asking about the series titled "date", and the third is asking about the first value present in the series "date".<br><br>

The first two rows that Python returned match what we expect them to, but the third shows that the values in the "date" series are formatted as a string and not as an actual date. <br><br>

To fix this, we use the .to_datetime function in Pandas:<br><br>

<img src="images/python9changedateformat.png?raw=true"><br><br>

Here we're also naming a new series (or column) in the "df" dataframe to BE the series "date" but formatted as a datetime. <br><br>

To check this, we used the same function as above:<br><br>

<img src="images/python10checkdatetype.png?raw=true"><br><br>

This shows the first value in the "date_clean" series is formatted as a timestamp in Pandas.<br><br>

To double check that the series was created in the dataframe, we can use **head** once more:<br><br>

<img src="images/python11shownewseries.png?raw=true"><br><br>



### Let's Specify!
Let's say that I am asked to look at specific columns in regards to specific data!<br><br>

<img src="images/python14impcols.png?raw=true"><br><br>

Let's say the Flotation Plant is looking at: % Iron Concentrate, % Silica Concentrate, Ore Pulp pH, Flotation Column 05 Level and all the data AFTER September 1st after 12pm. I will name a variable to equal the list of columns that we're looking at and include the date for further clarity. <br><br>

I then use **.loc** and specify that the rows I want returned need to be greater than Sep 1st at 12pm using the "date_clean" series and with those rows I want to look at "imp_cols" which include all the information that the plant is most interested in.<br><br>

This method is very useful in trimming down the database to pinpoint data that is relevant to the questions that are being asked. The use of variables in this instance helps to streamline my code so that I can efficiently manipulate the data to find the answers I'm searching for. <br><br>


### A Change in Parameters
Now my contact at the Flotation Plant is asking if I could extract data specifically between the dates of March 31st and June 2nd. Since this data is significant in my research to find insights, I am going to create its own dataframe and reset the index.<br><br>

<img src="images/python15dfjune.png?raw=true"><br><br>

I am asking Python to search within "df" the dates that are greater than March 31, 2017 @ 11:59pm AND less than June 2, 2017 within the "date_clean" series and then after returning those rows to RESET the index to finalize the NEW dataframe that I am naming "df_june". <br><br>



