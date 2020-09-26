### STextBlock
#### 支持的参数

* Text
* ColorAndOpacity
* Font
* TextStyle [^TextStyle]
* AutoWrapText
* Justification
* ShadowOffset
* MinDesiredWidth
* ToolTipText
* Visibility

**Example 1:**

    "STextBlock":
    {
        "Text": "TextBlock"
    }
**Example 2:**

    "STextBlock":
    {
        "Text": "Label Text",
        "ColorAndOpacity": [0,0.5,1,1],
        "Font": {
            "Style": "FEditorStyle",
            "StyleName": "FontAwesome.16"
        },
        "ShadowOffset": [2,2],
        "ShadowColorAndOpacity": [0,0,0,0.75],
        "Justification": "Right"
    }
**Example 3:**

    "STextBlock":
    {
        "Text": "A lot of text, ABCDEFG, HIJKLMN, OPQ, RST, UVW, XYZ. abcdefg, now i can sing my ABC.",
        "TextStyle": {
            "Style": "FEditorStyle",
            "StyleName": "LargeText"
        },
        "ColorAndOpacity": [1,1,1,1],
        "AutoWrapText": true,
        "Justification": "Center"
    }

#### 注意事项

* Justification选项有:
- Left
- Center
- Right

*  TextStyle: 支持“FEditorStyle”和“FCoreStyle”