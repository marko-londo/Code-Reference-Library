<h1 align="center">
	<img src="https://github.com/marko-londo/Code-Reference-Library/blob/main/Images/Header.png?raw=true" alt="Code-Reference-Library">
</h1>
<h1 align="center">
	<b>Code Reference Library</b>
<br>
</h1>
<h2 align="center">
    <em>Code snippets and descriptions with detailed commenting from some of my .ipynbs, serving as a reference for various coding topics.</em>
</h2>
<br>
<br>
<br>

### Table of Contents

- [Introduction](#introduction)
- [Imports](#imports)
  - [Pathlib](#pathlib)
    - [Path](#path)
  - [Pandas](#pandas)
  - [Matplotlib](#matplotlib)
    - [.pyplot](#pyplot)
    - [%matplotlib inline](#matplotlib-inline)
  - [Seaborn](#seaborn)
  - [Chardet](#chardet)
  - [Calendar](#calendar)
- [Function Documentation](#function-documentation)
  - [get_col_idx](#get-col-idx)
  - [shapes_by_month](#shapes-by-month)




<br>
<hr>
<br>
<h1 align="center">
	<img src="https://github.com/marko-londo/Code-Reference-Library/blob/main/Images/introduction.png?raw=true" alt="Introduction">
</h1>


## Introduction 
<br>This repository serves as an information library for data plotting and
analysis in Python. It contains a collection of useful functions and serves as
a reference for different coding topics. Additionally, it showcases visually appealing
plots to inspire and guide data visualization projects. The idea behind it was
to create a repo that is easy to navigate, to find specific use cases or
methods of aquiring results in a simplified way based on my own trial and error. This
repository will be regularly updated with new functions, interesting plots,
verbosely commented code snippets, and helpful examples.<br><br>

[Return to Top](#table-of-contents)
<br>
<br>
<hr>
<br>
<h1 align="center">
	<img src="https://github.com/marko-londo/Code-Reference-Library/blob/main/Images/Imports.png?raw=true" alt="Imports">

## Imports
<br>This section offers a brief overview of common imports and their uses. This
will help to find the specific library or module needed for a given task with a
concise description of each.<br><br>

- ### Pathlib

  Pathlib is a module that offers a simpler way to work with file systems and
  paths by representing them as objects, allowing for easy manipulation and
  platform-independent operations.

  - #### Path
   
    Path refers to the main class provided by the pathlib module. It
    represents a file system path as an object, enabling straightforward
    manipulation and operations on paths in a cross-platform manner.

    ```python
    from pathlib import Path

    path = Path(r"C:\Users\(...)\data.csv")
    ```
  
- ### Pandas

  Pandas is a powerful open-source Python library widely used for data
  manipulation and analysis. It provides data structures and functions to
  efficiently work with structured data, such as tables and time series,
  making it an essential tool for data scientists and analysts. Pandas allows
  for easy data cleaning, transformation, aggregation, and exploration, and
  offers various methods for handling missing data and dealing with diverse
  data formats. It also integrates well with other libraries in the Python
  ecosystem, making it a popular choice for data analysis tasks. It is
  generally aliased and imported as "pd"
  
  ```python
  import pandas as pd
  ```


- ### Matplotlib

  Matplotlib is a popular Python library used for creating static, animated,
  and interactive visualizations. It provides a wide range of plotting
  functionalities, allowing users to generate various types of charts,
  graphs, and plots with customizable features. Matplotlib is highly
  flexible, enabling users to create publication-quality visualizations for
  data analysis, scientific research, and data exploration tasks.
  
  - #### .pyplot
  
    .pyplot is a function provided by the matplotlib module that offers
    easy access to various plot types, including line, bar, box, scatter,
    and more. It is generally aliased and imported as "plt"
    ```python
    import matplotlib.pyplot as plt
    ```
  - #### %matplotlib inline
    
    The %matplotlib inline command is a specific Jupyter Notebook magic
    command used to enable the inline display of matplotlib plots within the
    notebook itself. By using this command, any plots generated by matplotlib
    will be shown directly in the output cell of the notebook, allowing for a
    seamless integration of code and visualizations in the notebook
    environment.
    ```python
    %matplotlib inline
    ```
- ### Seaborn
  
  Seaborn is a Python library for creating visually attractive statistical
  visualizations. It simplifies the process of generating common plots and
  provides additional features like color control and categorical data
  visualization. It is generally aliased and imported as "sns"
  
  ```python
  import seaborn as sns
  ```
- ### Chardet
  
  Chardet is a Python library for automatic character encoding detection. It
  helps determine the encoding of text or files when not explicitly specified.
  
  ```python
  import chardet

  df = pd.read_csv(path, encoding="Windows-1252") 
  
  # Sets encoding paramater to Windows-1252
  ```

- ### Calendar
  
  The "calendar" module in Python provides various functionalities for working with dates, months, and years. It allows you to generate calendars, manipulate dates, and perform calculations related to dates and time.

  With the calendar module, you can:

  * Generate calendars for a specific month or an entire year.
  * Access information about weekdays, weekends, and leap years.
  * Determine the day of the week for a given date.
  * Perform calculations like adding or subtracting days, weeks, or months from a given date.
  * Format dates in different ways, such as displaying them as strings or extracting specific components like the day, month, or year.
   
   
  The calendar module is useful for tasks that involve date and time
  calculations, scheduling, or displaying dates in a structured manner.

  ```python
  import calendar
  ```


[Return to Top](#table-of-contents)
<br>
<br>
<hr>
<br>
<h1 align="center">
	<img src="https://github.com/marko-londo/Code-Reference-Library/blob/main/Images/Functions.png?raw=true" alt=" Functions">

## Function Documentation
<br>This section provides documentation of functions I've created for
referencing.<br><br>

- ### get_col_idx
  
  This is a helpful function for quickly determining the index of a column in a
  dataframe.
  
  ```python
  import pandas as pd

  def get_col_idx(df):
    """
    This function takes in a dataframe and returns the index of each column.

    Parameters:
        df (pandas.DataFrame): The input dataframe.

    Returns:
        None

    """

    # Iterate over the columns of the dataframe
    for i, column in enumerate(df.columns):
        # Print the index of each column
        print(f"Index of column '{column}': {i}")
    ```
- ### shapes_by_month
  
  This function was used in a previous project analyzing UFO sightings data to determine the number of
  sightings by shape, by month. I had a df with one column called "Date / Time" and
  another called  "Shape". The "Date / Time" column contained dates and times (YYYY-MM-DD HH:MM:SS). The "Shape" column contained different "Shape" values for
  each sighting (Cone, Round, Light, etc.). I wanted to create a new df with an
  Index of just the months in str date/time format, and a column for each individual shape with the number of
  times each shape was sighted as a value.

  ***TLDR this function was used/ serves as an example to:*** 
  * Get the month from a series of YYYY-MM-DD HH:MM:SS values and set it as an
    index in a new df.<br>
  ***AND***
  * Extract str type value counts and set them as columns in that df.<br>

  ```python
  import pandas as pd
  import calendar

  def shapes_by_month(month_index):
      """
      Takes in month index and returns a df of shape counts by month.

      Parameters
      ----------
      month_index : int
          Month index of interest.

      Returns
      -------
      df : pd.DataFrame
          Dataframe of shape counts by month.

      Notes
      -----
      Month index starts at 1.
      """

      # Create a list of months from 1 to 12
      months = range(1, 13)

      # Create empty dictionaries to store dataframes
      data_by_month_df = {}
      shapes_by_month_df = {}

      # Iterate over each month
      for month in months:
          # Organize the data from the date/time column by month and add it to a 
          # series called  month_data
          month_data = ufo_filtered[ufo_filtered["Date / Time"].dt.month == month]

          # Create a dataframe for the filtered data and store it in the 
          # data_by_month_df dictionary
          data_by_month_df[month] = pd.DataFrame(month_data)

          # Create a dataframe of shape counts for the filtered data and store it 
          # in the shapes_by_month_df dictionary
          shapes_by_month_df[month] = pd.DataFrame(
              month_data["Shape"]
              .value_counts()
              .rename_axis("Shape")
              .reset_index(name="Count")
          )

      # Get the dataframe for the specified month index parameter and sort it by 
      # "Date / Time" column in ascending (chronological) order
      month = data_by_month_df[month_index].sort_values(by="Date / Time", ascending=True)

      # Count the number of occurrences of each shape in the specified month and create 
      # a dataframe
      month_shapes = (
          month["Shape"].value_counts().rename_axis("Shape").reset_index(name="Count")
      )

      # Add a "Month" column to the month_shapes dataframe with values ranging from 0 
      # to the number of unique shapes
      month_shapes["Month"] = list(range(len(month_shapes)))

      # Count the number of occurrences of each shape in the specified month and create 
      # a transposed dataframe
      shape_counts = (
          month["Shape"].value_counts().rename_axis("Shape").reset_index(name="Count")
      )
      month_df = pd.DataFrame(shape_counts).T

      # Set the column names of the `month_df` DataFrame to the values in the first row
      month_df.columns = month_df.iloc[0]

      # Drop the column named "Shape" from the `month_df` DataFrame
      month_df = month_df.drop("Shape")


      # Get the name of the specified month index, using the calendar module
      month_number = month_index
      month_name = calendar.month_name[month_number]

      # Set the index of month_df to be the month name
      month_df.index = pd.to_datetime([f"2000-{month_number:02d}-01"]).strftime("%B")

      # Return the final month_df dataframe
      return month_df

    ```
