# Orphan Records

```
OrphanRecords =
EXCEPT(
    DISTINCT(ChildTable[FKColumn]),
    DISTINCT(ParentTable[PKColumn])
)
```

* Explanation:
  - DISTINCT(ChildTable[FKColumn]): Gets all unique FK values from the child table.
  - DISTINCT(ParentTable[PKColumn]): Gets all unique PK values from the parent table.
  - EXCEPT: Returns the FK values from the child table that do not exist in the PK column of the parent table.
  - The order of arguments in EXCEPT matters because the first table shows the values to keep, and the second table contains the values to exclude.
