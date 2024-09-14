# Time-Based Comparisons – Growth Calculations


```
YoYGrowth = 
VAR CurrentValue = [TotalSales]
VAR PreviousValue = CALCULATE(
    [TotalSales], 
    DATEADD('Date'[Date], -1, YEAR) // Shifts the date back by 1 year
)
RETURN 
IF(
    NOT(ISBLANK(CurrentValue)) && NOT(ISBLANK(PreviousValue)),
    DIVIDE(CurrentValue - PreviousValue, PreviousValue, 0),
    BLANK()
)
```
* `IF` Statement with NOT(ISBLANK(...)): Checks if both CurrentValue and PreviousValue are not blank. This ensures that the measure only returns a result when both periods have data, avoiding errors or misleading results.
* `DIVIDE` Function: Calculates the percentage growth. The DIVIDE function is preferred over the / operator because it allows you to specify an alternate result (in this case, 0) if the denominator is zero, preventing division errors.
* `DATEADD`('Date'[Date], -1, YEAR): Moves the date context back by 1 year. This is functionally equivalent to SAMEPERIODLASTYEAR but gives you more control over the time interval. You can change the -1 to any number (negative or positive) and change YEAR to MONTH, QUARTER, or DAY to suit different comparisons.
