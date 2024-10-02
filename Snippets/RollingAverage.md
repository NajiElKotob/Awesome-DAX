# Rolling Average
`Rolling averages over time (a.k.a. moving averages or running averages)`

```
Sales R12M =
VAR NumOfMonths = 12
VAR LastCurrentDate =
    MAX ( 'Date'[Date] )
VAR Period =
    DATESINPERIOD ( 'Date'[Date], LastCurrentDate, - NumOfMonths, MONTH )
VAR Result =
    CALCULATE (
        AVERAGEX (
            VALUES ( 'Date'[Calendar Year Month] ),
            [Sales Amount]
        ),
        Period
    )
VAR FirstDateInPeriod = MINX ( Period, 'Date'[Date] )
VAR LastDateWithSales = MAX ( Sales[Order Date] )
RETURN
    IF ( FirstDateInPeriod <= LastDateWithSales, Result )
```



## References
* [Rolling 12 Months Average in DAX](https://www.sqlbi.com/articles/rolling-12-months-average-in-dax/) - sqlbi.com
