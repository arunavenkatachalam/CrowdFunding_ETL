# CrowdFunding_ETL
 
#Collaborators: Aruna Venkatachalam & Arshdeep Khurana

****#Created the Category and Subcategory DataFrames****

#Extracted and transformed the crowdfunding.xlsx Excel data to create a category DataFrame with the following columns:

    1. "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories
    2. "category" column that contains only the category titles

Exported the category DataFrame as category.csv and saved it to the GitHub repository.

Extracted and transformed the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:

     1. A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories
     2. A "subcategory" column that contains only the subcategory titles

Exported the subcategory DataFrame as subcategory.csv and saved it to the GitHub repository.

**Created the Campaign DataFrame**

Extracted and transformed the crowdfunding.xlsx Excel data to create a campaign DataFrame with the following columns:

    1. The "cf_id" column
    2. The "contact_id" column
    3. The "company_name" column
    4. The "blurb" column, renamed to "description"
    5. The "goal" column, converted to the float data type
    6. The "pledged" column, converted to the float data type
    7. The "outcome" column
    8. The "backers_count" column
    9. The "country" column
    10.The "currency" column
    11.The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
    12.The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
    13.The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
    14.The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

Exported the campaign DataFrame as campaign.csv and saved it to the GitHub repository.

**Create the Contacts DataFrame**

Both of the following methods were carried out to extract and transform the data from the contacts.xlsx Excel data:

A. Option 1: Use Python dictionary methods.

 1.Imported the contacts.xlsx file into a DataFrame.
 2.Iterated through the DataFrame, converting each row to a dictionary.
 3.Iterated through each dictionary, doing the following:
     Extracted the dictionary values from the keys by using a Python list comprehension.
     Added the values for each row to a new list.
     Created a new DataFrame containing the extracted data.
     Split each "name" column value into a first and last name, and placed each in a new column.
     Cleaned and exported the DataFrame as contacts.csv and saved it to the GitHub repository.

B. Option 2: Use regular expressions.

 1.Imported the contacts.xlsx file into a DataFrame.
 2.Extracted the "contact_id", "name", and "email" columns by using regular expressions.
 3.Created a new DataFrame with the extracted data.
 4.Converted the "contact_id" column to the integer type.
 5.Split each "name" column value into a first and a last name, and placed each in a new column.
 6.Cleaned and then exported the DataFrame as contacts_Regex.csv and saved to the GitHub repository.

**Create the Crowdfunding Database**

1. Inspected the four CSV files, and then sketched an ERD of the tables by using QuickDBDLinks to an external site.
2. Used the information from the ERD to create a table schema for each CSV file.
3. Saved the database schema as a Postgres file named crowdfunding_db_schema.sql, and saved it to the GitHub repository.
4. Created a new Postgres database, named crowdfunding_db.
5. Using the database schema, created the tables in the correct order to handle the foreign keys.
6. Verified the table creation by running a SELECT statement for each table. The SELECT statement required the table name to be encompassed in double quotes, for example, Select * from "Campaign". 
7. Imported each CSV file into its corresponding SQL table.
8. Verified that each table has the correct data by running a SELECT statement for each.
