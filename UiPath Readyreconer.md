# DataTable.Copy()
### DataTable.Copy() returns a DataTable with the structure and data of the DataTable.

```//Creating another DataTable to copy
DataTable dt_copy = new DataTable();
dt.TableName = "CopyTable";
dt_copy = dt.Copy();
```
---
# DataTable.Clone()
### Unlike Copy(), DataTable.Clone() only returns the structure of the DataTable, not the rows or data of the DataTable.
```//Creating another DataTable to clone
DataTable dt_clone = new DataTable();
dt.TableName = "CloneTable";
dt_clone = dt.Clone();
```
---
