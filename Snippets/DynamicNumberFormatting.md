# Dynamic Number Formatting


```
VAR CurrentValue = SELECTEDMEASURE()
RETURN
    SWITCH(
        TRUE(),
        CurrentValue <= 1E3, FORMAT(CurrentValue, "#,0.00"), // Display up to thousands
        CurrentValue <= 1E6, FORMAT(CurrentValue, "#,0,.00 K"), // Display thousands with K
        CurrentValue <= 1E9, FORMAT(CurrentValue, "#,0,,.00 M"), // Display millions with M
        CurrentValue <= 1E12, FORMAT(CurrentValue, "#,0,,,.00 B"), // Display billions with B
        FORMAT(CurrentValue, "#,0,,,.,00 T") // Display trillions with T
    )


```
