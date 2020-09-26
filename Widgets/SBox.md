### SBox
支持的参数

* HAlign
* VAlign
* Padding
* WidthOverride
* HeightOverride
* MinDesiredWidth
* MaxDesiredWidth
* MinDesiredHeight
* MaxDesiredHeight
* SetMaxDesiredHeight
* Content*
* ToolTipText
* Visibility

Slate Example:

Example 1:

    "SBox":
	{
        "Content": {
			"MinDesiredWidth": 200
            "MinDesiredHeight": 80,
            "SSlider": {
                "Orientation": "Vertical",
                "Value": 0.5,
                "Locked": false,
                "OnValueChanged": "print(%)"
            }
        }
    }


#### 注意事项
通常用于控制子组件的尺寸等

    

