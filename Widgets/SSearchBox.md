### SSearchBox
#### 支持的参数

* OnTextChanged
* OnTextCommitted
* DelayChangeNotificationWhiteTyping
* HintText
* SelectAllTextWhenFocused
* ToolTipText
* Visibility

Example 1:
    
    "SSearchBox": 
    {
        "HintText": "Type Search Text",
        "ToolTipText": "Tool Tip",
        "OnTextChanged": "print(%)",
        "OnTextCommitted": "print(%)",
        "SelectAllTextWhenFocused": false,
        "DelayChangeNotificationWhiteTyping": true
    }
    


#### 注意事项
OnTextChanged、OnTextCommitted 同SEditableText类似