### SComboBox
#### 支持的参数
* OptionsSource
* OnSelectionChanged
* ToolTipText
* Visibility

Example 1:

    "SComboBox": {
        "Aka": "CombBoxA",
        "Content": {
            "Text": "ComboBox"
        },
        "OptionsSource": [
            "OptionA",
            "OptionB",
            "OptionB"
        ],
        "OnSelectionChanged": "print(%)"
    }
#### 注意事项
OnSelectionChanged值为：状态修改时需要运行的python代码, **%** 将被OptionsSource中的选项值替换（例如Example 1中的 “OptionA”）


#### Python中设置界面的接口函数


**get_combo_box_selected_item**

获取当前SComboBox组件中被选中的选项值

py help:

    get_combo_box_selected_item(...)
        x.get_combo_box_selected_item(aka_name) -> str or None
        Get Combo Box Selected Item
        
        Args:
            aka_name (Name): 
        
        Returns:
            str or None: 
        
            out_item (str):


**set_combo_box_selected_item**

设置当前SComboBox组件中被选中的选项
			
py help:    

    set_combo_box_selected_item(...)
        x.set_combo_box_selected_item(aka_name, index) -> bool
        Set Combo Box Selected Item
        
        Args:
            aka_name (Name): 
            index (int32): 
        
        Returns:
            bool: