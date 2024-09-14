# Selected Value or Default

This measure returns the selected value from the slicer on 'Table'[Column]. If no selection is made, it returns "No Selection". If multiple selections are made, it returns BLANK().

```
SelectedValueOrBlank =
VAR SelectedValue = SELECTEDVALUE('Table'[Column])
RETURN
IF(
    ISBLANK(SelectedValue),
    BLANK(),
    SelectedValue
)
```

* `VAR` SelectedProductName: Stores the selected product name from the slicer on 'Products'[ProductName]. The variable name explicitly describes the content it holds.
* `SELECTEDVALUE`('Products'[ProductName]): Retrieves the selected product name. If no single selection is made (either no selection or multiple selections), it returns BLANK().
* `RETURN` Statement: Uses an IF statement to check whether SelectedProductName is BLANK():
  - If SelectedProductName is `BLANK()`, it returns "No Selection".
  - If SelectedProductName has a value, it returns SelectedProductName.
