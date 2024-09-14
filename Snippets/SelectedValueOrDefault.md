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
