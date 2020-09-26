### SListView
#### 支持的参数


* ListItemsSource
* OnSelectedChanged
* OnContextMenuOpening
* OnMouseButtonDoubleClick
* SHeaderRow
* ToolTipText
* Visibility

Example 1:

    "SListView": {
        "ItemHeight": 10,
        "Aka": "AList",
        "ListItemsSource": ["Item A", "Item B", "Item C"],
        "SHeaderRow": {
            "Columns": [
                {
                    "DefaultLabel": "List Label",
                    "FillWidth": 1
                }
            ]
        },
        "OnContextMenuOpening":
        {
            "items":
            [
                {
                    "name": "ContextMenu A",
                    "Command": "print ('ContextMenu A')"
                },
                {
                    "name": "ContextMenu B",
                    "Command": "print ('ContextMenu B')"
                }
            ]
        },
        "OnSelectedChanged": "print ('Selected: {}  index: {}'.format(%item, %index))",
        "OnMouseButtonDoubleClick": "print ('Double click: {}  index: {}'.format(%item, %index))"
    }

#### 注意事项
OnSelectedChanged：需要运行的python代码, **%item** 为实际选中的选项值, **%index** 选项索引
OnMouseButtonDoubleClick：同上
OnContextMenuOpening：右键菜单，语法与ContentBrower中相同


#### Python中设置界面的接口函数

**set_list_view_items**
				
设置SListView中的items内容
	
py help:   
	
    set_list_view_items(...)
        x.set_list_view_items(aka_name, str_array) -> None
        Set List View Items
        
        Args:
            aka_name (Name): 
            str_array (Array(str)):

**get_list_view_items**

获取SListView中的items内容

py help:
			
    get_list_view_items(...)
        x.get_list_view_items(aka_name) -> (str_array=Array(str), item_stats=Array(int32))
        Get List View Items
        
        Args:
            aka_name (Name): 
        
        Returns:
            tuple: 
        
            str_array (Array(str)): 
        
            item_stats (Array(int32)):
			
**set_list_view_selections**

设置SListView中的选中项	

py help:
	
    set_list_view_selections(...)
        x.set_list_view_selections(aka_name, indexes) -> None
        Set List View Selections
        
        Args:
            aka_name (Name): 
            indexes (Array(int32)):