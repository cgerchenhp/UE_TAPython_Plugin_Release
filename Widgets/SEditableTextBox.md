### SEditableTextBox
#### 支持的参数

* Text
* HintText
* Justification
* IsReadOnly
* OnTextCommitted
* OnTextChanged
* MinDesiredWidth
* ToolTipText
* Visibility

Example 1:

    "SEditableTextBox":
    {
        "Text": "Read only SEditableTextBox",
        "IsReadOnly": true
    }
Example 2:	

    "SEditableTextBox":
    {
        "Text": "",
        "SelectAllTextWhenFocused": true,
        "HintText": "Type some thing, and press enter",
        "OnTextChanged": "print(%)",
        "OnTextCommitted": "print('input text: {}'.format(%))"
    }

#### 注意事项
OnTextChanged的值应为：字符串修改时运行的python代码，**%** 符号将被Text的内容所替换
例如

    print(%)
	
OnTextCommitted：同上，在输入时运行