# Cleaning-Data
-- Remove Duplicates 
-- Standardize the Data 
-- Null Values or Blank values 
-- Remove Any Columns or Rows
I'm using MySQL to clean data from raw form, saving raw file as Table for reference and all other changes will be executed in Table number 2.
I created a new column counting how many duplicate in my data file (using Window function to define the partitioning and ordering of the rows) based on some important column names, while in a real world of cleaning data, I personally think we would have a primary column such as ID, it would be much easier!
I filtered out all rows have result more than 1 in Count column by using CTE, then I delete them or I would create a new table and delete directly in it.
When stadardizing the data, I used TRIM, UPDATE, LIKE most of the time or changed format by ALTER TABLE (the format should be checked and standardized when uploading file).
Regarding blank data, I usually change it into NULL value and fill it by comparing with other similar rows (using JOIN the table itself or something with another table and UPDATE accordingly)
When dealing with NULL, I'm trying not to delete them because it might affect the result of analysing, I want to fill them all as much as I can.
And eventually, I used DROP to remove any unneccesory columns or rows, in this project, I deleted Count row that I created initially for removing duplicates.
