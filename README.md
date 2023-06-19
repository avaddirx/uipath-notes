# UiPath-Notes
## Convert DT column to list 
```List(of string) = ( From row in dt.AsEnumerable() Select Convert.Tostring(row(“ColumnName”)) ).ToList()```
## Compare the elements of a list to each value of data row and output the elements that did not match into a datatable
```yourList.Except((From x In yourDT.AsEnumerable Let ID = x.Item(“ID”).ToString Select ID)).ToList```
## Rename Column Name in Datat Table
```yourDataTable.Columns(0).ColumnName = "New Column Name"```
or
```yourDataTable.Columns("oldColumnName").ColumnName = "New Column Name"```
## Convert a DataTable column into an Array
* to get string array
```DT_name.AsEnumerable.Select(Function (x) x(YourColNameOrIndex).toString).toArray```
* to get unique values 
```DT_name.AsEnumerable.Select(Function (x) x(YourColNameOrIndex).toString).Distinct().toArray```
## Convert Data Row to array 
inside for For Each Row ```CurrentRow.ItemArray```

## Filter data table with Filter arguments 
```(From d In  yourDT.AsEnumerable Let check = yourFilterargs.Any(Function (x) d("SubmissionProfileName").ToString.ToUpper.Trim.Equals(x.ToUpper.Trim)) Where check Select r=d).CopyToDataTable```

## Skip Top two rows in the data table 
```DataTable_Variable.AsEnumerable.Skip(2).CopyToDataTable```

## Skip Top two rows in the data table and add a filter to it so you do two things at once
```DataTable_Variable.AsEnumerable.Skip(2).Where(Function(r) r(0).ToString.Trim<>"" ).CopyToDataTable```
## Remove header in the data table
```MyDataTableText``` = ```MyDataTableText.Remove(0, MyDataTableText.IndexOf(Environment.NewLine)+2)```
or 
```Dt.AsEnumerable.Skip(1).CopyToDataTable```
## Dispacher: Datatable —> String —> Orchestrator
```YourQueueString = Newtonsoft.Json.JsonConvert.SerializeObject(YourDataTable)```

## Performer: Orchestrator —> String —> Datatable
```QueueItemData = Newtonsoft.Json.JsonConvert.DeserializeObject(Of DataTable)(out_TransactionItem.SpecificContent("YourQueueString").ToString)```
QueueItemData will result as a Datatable.


https://forum.uipath.com/t/getting-datatable-headers-as-variables/273043/8
