### SButton
#### 支持的参数

* Text
* OnClick
* ContentPadding
* HAlign
* VAlign
* ToolTipText
* Visibility

Example 1:

        "SButton":
        {
            "Text": "Button Label",
            "OnClick": "print('Button clicked.')"
        }

Example 2:


    "SButton":
    {
        "Text": "Colored Button",
        "HAlign": "Center",
        "ContentPadding": 6,
        "ButtonColorAndOpacity": [0,0.5,1,1],
        "ForegroundColor": [1,1,1,1],
        "ToolTipText": "按钮工具提示，鼠标悬停时显示",
        "OnClick": "print('Button clicked.')"
    }

#### 注意事项
OnClick的值应为：点击时需要运行的python代码