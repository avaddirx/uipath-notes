# uipath-notes
# Convert DT column to list 
```List(of string) = ( From row in dt.AsEnumerable() Select Convert.Tostring(row(“ColumnName”)) ).ToList()```
