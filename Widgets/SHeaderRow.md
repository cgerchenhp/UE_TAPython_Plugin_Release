### SHeaderRow
#### 支持的参数

* Columns
* DefaultLabel
* FillWidth
* ToolTipText
* Visibility

Example 1:

    "SHeaderRow": {
        "Columns": [
            {
                "DefaultLabel": "List Label",
                "FillWidth": 1
            }
        ]
    }
#### 注意事项

#### Python中设置界面的接口函数

**add_column**

为SHeadRow添加一个Column

py help:
			
    add_column(...)
        x.add_column(aka_name, label) -> None
        Head Row
        
        Args:
            aka_name (Name): 
            label (str):

**set_column_lable**
			
设置SHeadRow中指定Column中的Label文字
	
py help:
			
    set_column_lable(...)
        x.set_column_lable(aka_name, index, label) -> None
        Set Column Lable
        
        Args:
            aka_name (Name): 
            index (int32): 
            label (str):
