### SBorder
#### 支持的参数:

* BorderImage


Example:

    "SBorder":
    {
        "Content":
        {
            "SSpacer":
            {
                "Size": [100, 50]
            }
        }
    }

    "SBorder":
    {
        "BorderImage":
        {
            "Style": "FEditorStyle",
            "Brush": "ToolPanel.DarkGroupBorder"
        },
        "Content":{
            "SSpacer":{
                "Size": [100, 50]
            }
        }
    }


#### 注意事项：
“Style”目前支持“FCoreStyle”和“FEditorStyle”
