### Slots
这里将不同类型的Slot统称为Slots,不直接显式写"SSlots"，通常在SVerticalBox，SHorizoontalBox的"Slots"中使用
### 支持的父物体控件
* SGridPanel
* SScrollBox
* SVerticalBox
* SHorizontalBox
* SBox


Example 1:

    "SScrollBox": {
        "Slots":
        [
            {
                "Padding": 5,
                "SVerticalBox":
                {
                    "Slots": [
                        {
                            "padding": 2,
                            "SButton": {
                                "Text": "Button A"
                            }
                        },
                        {
                            "padding": 2,
                            "SButton": {
                                "Text": "Button B"
                            }
                        }
                    ]
                }
            }
        ]
    }
        

#### 支持的参数

* Padding
* AutoHeight
* AutoWidth
* VAlign
* HAlign
* FillWidth


Example:
    
      
#### 注意事项


- autoHeight: 支持SVerticalBox
- autoWidth: 支持SHorizontalBox和SHeader
- VAlign/HAlign: 支持SVerticalBox/SHorizontalBox
- FillWidth: 支持SHorizontalBox 和 SHeaderRow
