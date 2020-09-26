### SCheckBox
#### 支持的参数

* HAlign
* Padding
* OnCheckStateChanged
* IsChecked
* CheckBoxStyle
* ToolTipText
* Visibility
* Content

Example 1:

    "SCheckBox":{
        "Content":
        {
            "STextBlock": {
                "Text": "Check Box Label"
            }
        },
        "IsChecked": true,
        "OnCheckStateChanged": "print(%)"
    }
    
Example 2:
	
    "SCheckBox":
    {
        "Content": {
            "HAlign": "Center",
            "SBox": {
                "VAlign": "Center",
                "HAlign": "Center",
                "Padding" : [10, 10],
                "Content":
                {
                    "STextBlock":
                    {
                        "Text": "Toggle Button 本质上是个SCheckBox"
                    }
                }
            }
        },
        "CheckBoxStyle": {
            "Style": "FCoreStyle",
            "StyleName": "ToggleButtonCheckbox"
        },
        "Padding": 6,
        "IsChecked": true,
        "OnCheckStateChanged": "print('checked: %'.format(%))"
    }
#### 注意事项
OnCheckStateChanged值为：状态修改时需要运行的python代码, **%** 为IsChecked值，True/False


