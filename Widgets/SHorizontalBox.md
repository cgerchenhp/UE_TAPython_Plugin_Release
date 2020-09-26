### SHorizontalBox
#### 支持的参数

* Padding
* AutoWidth
* HAlign
* VAlign
* Slots

Example 1:

    "SHorizontalBox": 
	{
        "Slots": [
            {
                "STextBlock":
                {
                    "Text": "SBreadcrumbTrail"
                }
            },
            {
                "Padding": [10, 0],
                "SButton":
                {
                    "Text": "Add",
                    "HAlign": "Center",
                    "VAlign": "Center",
                    "OnClick": "gallery.push_breadcrumb()"
                }
            }
        ]
    }
      
#### 注意事项

HAlign 选项有：
* Fill
* Left
* Center
* Right

VAlign 选项有：
* Fill
* Top
* Center
* Right


Padding 为针对每个Slot设置，应写在单个Slot中，如上例

padding 支持 scaler、Vector2、Vector4形式，例如
- "Padding" : 4			
- "Padding" : [4, 8]		//左右、上下
- "Padding" : [2, 4, 6, 8]  //左、上、右、下