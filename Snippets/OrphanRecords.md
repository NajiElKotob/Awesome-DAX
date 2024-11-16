# Orphan Records

```
OrphanRecords =
EXCEPT(
    DISTINCT(ChildTable[FKColumn]),
    DISTINCT(ParentTable[PKColumn])
)
```
