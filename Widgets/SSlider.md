### Slider
#### 支持的参数
* Text
* Locked
* Value
* OnValueChanged
* ToolTipText
* Visibility

Example 1:

    "SSlider":
        {
            "Orientation": "Horizontal",
            "Value": 0.5,
            "Locked": false,
            "OnValueChanged": "print(%)"
        }
    
    
#### 注意事项
Orientation 可选项有：
- Horizontal
- Vertical

OnValueChanged：需要运行的python代码，**%** 为Value