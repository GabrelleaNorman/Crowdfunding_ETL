# Crowdfunding_ETL

*Instructions

The instructions for this mini project are divided into the following subsections:

- Create the Category and Subcategory DataFrames

- Create the Campaign DataFrame

- Create the Contacts DataFrame

- Create the Crowdfunding Database

*Create the Category and Subcategory DataFrames

1. Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:

    A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories

    A "category" column that contains only the category titles

The following image shows this category DataFrame:
![image](https://github.com/GabrelleaNorman/Crowdfunding_ETL/assets/130908954/9a96512b-7d6f-440e-a273-1201bf844a0b)




2. Export the category DataFrame as category.csv and save it to your GitHub repository.

3. Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:

    A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories

    A "subcategory" column that contains only the subcategory titles

    The following image shows this subcategory DataFrame:

![image](https://github.com/GabrelleaNorman/Crowdfunding_ETL/assets/130908954/bd250227-274f-4512-87cd-3d36e49f75be)


4. Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository.

*Create the Campaign DataFrame

1. Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns:

    The "cf_id" column

    The "contact_id" column

    The "company_name" column

    The "blurb" column, renamed to "description"

    The "goal" column, converted to the float data type

    The "pledged" column, converted to the float data type

    The "outcome" column

    The "backers_count" column

    The "country" column

    The "currency" column

    The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format

    The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format

    The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame

    The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

    The following image shows this campaign DataFrame:
   ![image](https://github.com/GabrelleaNorman/Crowdfunding_ETL/assets/130908954/4a4309fd-99b8-4521-aaf9-ae01b23d6122)




2. Export the campaign DataFrame as campaign.csv and save it to your GitHub repository.

*Create the Contacts DataFrame

1. Choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:

**For this project we chose Option 1**


*Option 1: Use Python dictionary methods.



2. If you chose Option 1, complete the following steps:

    Import the contacts.xlsx file into a DataFrame.

    Iterate through the DataFrame, converting each row to a dictionary.

    Iterate through each dictionary, doing the following:

    Extract the dictionary values from the keys by using a Python list comprehension.

    Add the values for each row to a new list.

    Create a new DataFrame that contains the extracted data.

    Split each "name" column value into a first and last name, and place each in a new column.

    Clean and export the DataFrame as contacts.csv and save it to your GitHub repository.



3. Check that your final DataFrame resembles the one in the following image:

![image](https://github.com/GabrelleaNorman/Crowdfunding_ETL/assets/130908954/3cdcd5ea-7342-4635-8333-1bbea272c191)


*Create the Crowdfunding Database

    1. Inspect the four CSV files, and then sketch an ERD of the tables by using QuickDBDLinks to an external site..

    2. Use the information from the ERD to create a table schema for each CSV file.

            Note: Remember to specify the data types, primary keys, foreign keys, and other constraints.

    3. Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository.

    4. Create a new Postgres database, named crowdfunding_db.

    5. Using the database schema, create the tables in the correct order to handle the foreign keys.

    6. Verify the table creation by running a SELECT statement for each table.

    7. Import each CSV file into its corresponding SQL table.

    8. Verify that each table has the correct data by running a SELECT statement for each.

Hints

To split each "category & sub-category" column value into "category" and "subcategory" column values, use df[["new_column1","new_column2"]] = df["column"].str.split(). Make sure to pass the correct parameters to the split() function.

To get the unique category and subcategory values from the "category" and "subcategory" columns, create a NumPy array where the array length equals the number of unique categories and unique subcategories from each column. For information about how to do so, see numpy.arangeLinks to an external site. in the NumPy documentation.

To create the category and subcategory identification numbers, use a list comprehension to add the "cat" string or the "subcat" string to each number in the category or the subcategory array, respectively.

For more information about creating a new Pandas DataFrame, see the pandas.DataFrameLinks to an external site. in the Pandas documentation.

To convert the "goal" and "pledged" columns to the float data type, use the astype() method.

To convert the "launch_date" and "end_date" UTC times to the datetime format, see the Transform_Grocery_Orders_Solved.ipynb activity solution.

For more information about how to add the "category_id" and "subcategory_id" unique identification numbers to the campaign DataFrame, see the pandas.DataFrame.mergeLinks to an external site. in the Pandas documentation.
