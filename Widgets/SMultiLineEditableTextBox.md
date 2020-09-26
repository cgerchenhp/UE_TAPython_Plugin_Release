### SMultiLineEditableTextBox
#### 支持的参数

* Text
* HintText
* IsReadOnly
* AutoWrapText
* Margin
* Padding
* ToolTipText
* Visibility

Example 1:

    "SMultiLineEditableTextBox": 
	{
        "Text": "Muti-line Box\nLine 1\nLine 2\nLine 3",
        "HintText": "This is a SMultiLineEditableTextBox",
        "AutoWrapText": true
    }

Example 2:	

    "SMultiLineEditableTextBox": 
	{
        "Text": "Muti-line Box\nLine 1\nLine 2\nLine 3",
        "HintText": "This is a SMultiLineEditableTextBox",
        "ToolTipText": "Read only",
        "Padding": 10,
        "IsReadOnly": false,
        "AutoWrapText": true
    }
	
	
#### 注意事项
OnTextChanged：同SEditableText
OnTextCommitted：同SEditableText 


#### Padding和Margin的区别：

SMultiLineEditableTextBox 可以看作是一个有SHorizontalBox和SVerticalBox嵌套包裹着的SMutiLineEditableText

Padding的空余来自SHorizontalBox和SVerticalBox，边缘面积不属于SMutiLineEditableText；而Margin的空余来自SMutiLineEditableText本身

#### Python中设置界面的接口函数

**set_text**

设置组件中的文本内容，支持的组件类型有：
- SEditableText
- SEditableTextBox
- SMultiLineEditableText
- SMultiLineEditableTextBox
		
py help:

    set_text(...)
        x.set_text(aka_name, text) -> None
        Set Text
        
        Args:
            aka_name (Name): 
            text (str):
			
**get_text**

获取组件中的文本内容，支持的组件类型同上
		
py help:

    get_text(...)
        x.get_text(aka_name) -> str or None
        Get Text
        
        Args:
            aka_name (Name): 
        
        Returns:
            str or None: 
        
            out_text (str):