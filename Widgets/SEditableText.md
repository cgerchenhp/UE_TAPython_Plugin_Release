### SEditableText
#### 支持的参数

* MinDesiredWidth
* Text
* ColorAndOpacity
* OnTextChanged
* OnTextCommitted
* Font
* MinDesiredWidth
* HintText
* IsReadOnly
* SelectAllTextWhenFocused

Example 1:

    "SEditableTextBox":
    {
        "Text": "Type some thing, and press enter",
        "OnTextChanged": "print(%)",
        "AutoWrapText": true,
        "SelectAllTextWhenFocused": true,
        "OnTextCommitted": "print('input text: {}'.format(%))"
    }
	
Example 2:

    "SEditableTextBox":
    {
        "Text": "Read only SEditableTextBox",
		"HintText": "Can't edit",
        "IsReadOnly": true
    }

#### 注意事项
OnTextChanged的值应为：字符串修改时运行的python代码，**%** 为Text内容
例如

    print(%)
	
OnTextCommitted：同上，在输入时运行