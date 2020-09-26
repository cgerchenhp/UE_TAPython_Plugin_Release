### SVerticalBox
#### 支持的参数

* Padding
* AutoHeight
* Slots

Example 1:

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