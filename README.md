# uipath-notes
# Convert DT column to list 
```List(of string) = ( From row in dt.AsEnumerable() Select Convert.Tostring(row(“ColumnName”)) ).ToList()```
# Compare the elements of a list to each value of data row and output the elements that did not match into a datatable
```yourList.Except((From x In yourDT.AsEnumerable Let ID = x.Item(“ID”).ToString Select ID)).ToList```
# Rename Column Name in Dtat Table
```yourDataTable.Columns(0).ColumnName = "New Column Name"```
or
```yourDataTable.Columns("oldColumnName").ColumnName = "New Column Name"```
