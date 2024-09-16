# Dynamic Number Formatting


```
VAR CurrentValue = SELECTEDMEASURE() // Store the selected measure value in a variable
RETURN
    SWITCH(
        TRUE(), // Start checking conditions in order
        CurrentValue <= 1E3, "#,0.00", // Format as a standard number if <= 1,000
        CurrentValue <= 1E6, "#,0,.00 K", // Format in thousands (K) if <= 1 million
        CurrentValue <= 1E9, "#,0,,.00 M", // Format in millions (M) if <= 1 billion
        CurrentValue <= 1E12, "#,0,,,.00 B" // Format in billions (B) if <= 1 trillion
    )

```

## References

### Articles
* [Introducing dynamic format strings for DAX measures](https://www.sqlbi.com/articles/introducing-dynamic-format-strings-for-dax-measures/) - sqlbi.com

