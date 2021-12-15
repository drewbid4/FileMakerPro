# Summary

I am using this repository as a place to track changes made to different scripts and processes within FileMaker Pro Advanced.

## Current Focus
- sending data to SQL Server on a schedule
- exporting data from FileMaker Pro to improve performance

# Proposed Process
1. Check for unprocessed records (ExecuteSQL calc)
2. Search for the unprocessed records
3. Generate field list variable
4. Loop through up to 1000 records to generate data list variable
5. Push data to SQL
6. Continue looping until all found set is processed

credit: found via soliant consulting website (https://www.soliantconsulting.com/blog/executesql-filemaker/)

# ExecuteSQL 

There are two types of ExecuteSQL steps in FileMaker Pro: a script step and a function. Use the Script Step to interact with ODBC data sources, and use the function
to interact with data within the FileMaker Pro file.

## ExecuteSQL Script Step
- Execute SQL script step performs SQL statements against ODBC data sources, not FileMaker data sources
- to query tables in a FileMaker data source using only SQL SELECT statements, use the ExecuteSQL function
- this provides more control over the interaction with ODBC data sources
- SQL Server supports both unicode and non-unicode field types; you must prefix all Unicode strings with an uppercase "N"


## ExecuteSQL Function
- Executes a SQL query for the specified table occurence in a FileMaker Pro Advanced file
- ExecuteSQL does not recognize relationships created in FileMaker Pro Advanced, which gives flexibility to define relationships regardless of layout context
- Use _arguments_ for dynamic parameters within the SQL statement (specify dynamic parameters within the statement by using the (?) character)

## Notes
- To avoid issues with field name formatting in queries use the following: BACKSLASH"[field name]BACKSLASH"
- cast timestamps as DATE fields
