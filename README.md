# Summary

I am using this repository as a place to track changes made to different scripts and processes within FileMaker Pro Advanced.

## Current Focus
- sending data to SQL Server on a schedule
- exporting data from FileMaker Pro to improve performance

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
