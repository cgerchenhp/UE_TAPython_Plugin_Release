### SSpinBox
#### 支持的参数
* Type
* MinValue
* MaxValue
* MinSliderValue
* MaxSliderValue
* Delta
* Value
* ToolTipText
* Visibility
* OnValueChanged

Example 1:

    "SSpinBox": 
	{
        "Type": "int",
        "Value": 10,
        "MinValue": 1,
        "MaxValue": 8192,
        "MinSliderValue": 1,
        "maxSliderValue": 8192,
        "Delta": 1,
        "OnValueChanged": "print(%)"
    }

#### 注意事项


- type: 支持integer或者float
- OnValueChanged：需要运行的python函数，**%** 为Value
