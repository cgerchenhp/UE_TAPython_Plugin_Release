### SHeader
#### 支持的参数


* ToolTipText
* Visibility
* Content

Example 1:

    "SHeader":
    {
        "Content":
        {
            "STextBlock":
            {
                "Text": "A Header",
                "Justification": "Center"
            }
        }
    }
#### 注意事项
SHeader 实际是一个默认有三个元素的SHorizontalBox，Content中除了常见的STextBlock，也可以是其他组件