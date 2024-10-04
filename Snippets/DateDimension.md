# Date Dimension
```
Calendar = 
ADDCOLUMNS(
                CALENDAR("2017-01-01",TODAY()), //Date Table
                "Year", Year([Date]), //Year
                "Quarter", CONCATENATE("Q",ROUNDUP(MONTH([Date])/3,0)),//Quarter e.g. Q1, Q2,...
                "Month", MONTH([Date]), //Month
                "MonthName", FORMAT([Date],"MMMM"), //Day Name e.g. January. MMM -> Jan, MM -> 01, M -> 1
                "WeekNumber", WEEKNUM([Date]), //Week Number 1 - 52
                "WeekDay",WEEKDAY([Date]), //Week Day 1 - 7
                "Day", DAY([Date]), //Day
                "DayName", FORMAT([Date],"DDDD") //Day Name e.g. Monday, Sunday. DDD -> Mon, DD -> 01, D-> 1
                )
```
* References:
  - CALENDAR Function (Returns a table with a single column named “Date” that contains a contiguous set of dates) https://msdn.microsoft.com/en-us/query-bi/dax/calendar-function-dax
  - ADDCOLUMNS Function (Adds calculated columns to the given table or table expression) https://msdn.microsoft.com/en-us/query-bi/dax/addcolumns-function-dax
  - Date and Time DAX Functions https://msdn.microsoft.com/en-us/query-bi/dax/date-and-time-functions-dax
  - FORMAT Function (Converts a value to text accrding to the specified format) https://msdn.microsoft.com/en-us/query-bi/dax/format-function-dax
  - CONCATENATE Function (Joins two text strings into one text string) https://msdn.microsoft.com/en-us/query-bi/dax/concatenate-function-dax
  - ROUNDUP Function (Rounds a number up, away from 0 (zero) https://msdn.microsoft.com/en-us/query-bi/dax/roundup-function-dax
