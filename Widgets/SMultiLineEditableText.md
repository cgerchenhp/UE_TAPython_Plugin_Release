### SMultiLineEditableText
#### 支持的参数

* Text
* HintText
* IsReadOnly
* SelectAllTextWhenFocused
* AutoWrapText
* Margin
* Padding
* ToolTipText
* Visibility

Example 1:

    "SMultiLineEditableTextBox": {
        "Text": "Multi-line Box\nMargin可以控制4个方向的空白可以以下几种写法\nMargin: 10\nMargin: [0, 10] 上下留空\nMargin: [0, 2, 4, 6] 左上右下分别为0，2，4，6",
        "HintText": "This is a SMultiLineEditableTextBox",
        "Margin": [10,0],
        "ToolTipText": "Tool Tips",
        "AutoWrapText": true
    }

Example 2:

    "SMultiLineEditableText":
    {
        "Text": "line 1 \nline 2 \nline 3",
        "HintText": "SelectAllTextWhenFocused",
        "Font": {
            "Style": "FEditorStyle",
            "StyleName": "FontAwesome.16"
        },
        Margin: 10,
        "SelectAllTextWhenFocused": true,
        "OnTextChanged": "print(%)",
        "OnTextCommitted": "print('input text: {}'.format(%))"
    }

#### 注意事项

OnTextChanged的值应为：字符串修改时运行的python代码，**%** 符号将被Text的内容所替换
例如

    print(%)
	
OnTextCommitted：同上，在输入时运行


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