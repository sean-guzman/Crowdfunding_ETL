# Crowdfunding_ETL (Project 2)

Sean Guzman

Rutgers Data Sciences Bootcamp, Project 2 (15 May 2023)

For this project, the task at hand is to Extract, Transorm, and Load (ETL).

* Extract - first, read two excel files (contacts.xlsx and crowdfunding.xlsx),
* Transform - then clean and structure this data into smaller relational tables/dataframes exported into serparate csv files
* Load - and lastly, load the csv files into a database using PostgresSQL.

Using Jupyter Notebook, the 'category & sub-category' column from the crowdfunding spreadsheet was first extracted and separated into two columns with its own unique identifiers, then put into two dataframes, category and sub-category, then exported to csv files (category.csv and subcategory.csv).  The table itself was then transformed to have the following columns, renamed and types adjusted:
* 'cf_id'
* 'contact_id'
* 'company_name'
* 'blurb', renamed to 'description'
* 'goal', converted to float data type
* 'pledged' column, converted to float data type
* 'outcome' column
* 'backers_count' column
* 'country' column
* 'currency' column
* 'launched_at' column, renamed to 'launch_date', with the UTC times converted to the datetime format
* 'deadline' column, renamed to 'end_date', with the UTC times converted to the datetime format
* 'category_id' column, with unique identification numbers matching those in the 'category_id' column of the * category DataFrame
* 'subcategory_id' column, with the unique identification numbers matching those in the 'subcategory_id' column of the subcategory DataFrame

All other columns, including the original 'category & sub-category' column were dropped.  This dataframe was then exported into a csv file, entitled campaign.csv.

Using Python dictory methods on the contacts spreadsheet, the data was extracted into a dataframe, iterating through each row in a for loop, separating its keys and values into separate columns.  The cleaned dataframe was then exported into 
a csv file, entitled contacts.csv.

Using https://app.quickdatabasediagrams.com, an entity relationship diagram of the four exported csv files (campaign, category, contacts, and subcategory) was created determining the relationship between each csv file, and identifying its primary and foreign keys.  The table schema was exported then imported into a database in PostgreSQL, where further queries can be made.
