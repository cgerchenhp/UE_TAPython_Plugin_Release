### SGridPanel
#### 支持的参数

* FillColumn
* Column_Row
* Slots
* ToolTipText
* Visibility

Example 1:

    "SGridPanel":
    {
       "FillColumn": [[0,0.5],[1,0.5]],
       "Slots":
       [
           {
               "Column_Row": [0,0],
               "STextBlock":
               {
                   "Text": "SBorder"
               }
           },
           {
               "Column_Row": [1,0],
               "SBorder":
               {
                   "Content":
                   {
                       "SSpacer":
                       {
                           "Size": [100, 50]
                       }
                   }
               }
           }
        ]
    }

对应的Slate：

    SNew(SGridPanel)
        .FillColumn(0, 0.5f)
        .FillColumn(1, 0.5f)
        + SGridPanel::Slot(0, 0)
        [
        	SNew(STextBlock)
        	.Text(LOCTEXT("SBorderLabel", "SBorder"))
        	
        ]
        + SGridPanel::Slot(1, 0)
        .Padding(0.0f, 4.0f)
        [
        	SNew(SBorder)
        	[
                SNew(SSpacer)
                .Size(FVector2D(100, 50))
            ]
        ]
        +SGridPanel::Slot(0, 1)[
            SNew(STextBlock)
                .Text(LOCTEXT("SBorderWithBrush", "SBorder With Brush"))
        ]
        + SGridPanel::Slot(1, 1)
        .Padding(0.0f, 4.0f)
        [
            SNew(SBorder)
            .BorderImage(FEditorStyle::Get().GetBrush("ToolPanel.DarkGroupBorder"))
            [
                SNew(SSpacer)
                .Size(FVector2D(100, 50))
            ]
        ]
   
    
#### 注意事项