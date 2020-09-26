# UE4 Python Tools Doc
一款努力让“开发UE4编辑器工具”如同“开发Max脚本工具”一样简单的插件

![ObjectDetailViewer.png](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/ObjectDetailViewer.png)
![PyModelRenderer.png](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/PyModelRenderer.png)



## 功能介绍
该插件可以通过可配置的Json文件创建动态的编辑器菜单和工具UI界面，并将其于Python脚本相关联，做到编辑器工具Python化。降低工具开发的难度、加快工具迭代速度

## 功能特色
- UE4原生Python支持，动态解析，无需编译
- 不改引擎，无需Editor UMG支持，兼容低版本UE4
- 可配置的主菜单/工具栏/Content Brower 入口
- 伪Slate语法，动态实时预览界面效果
- 标准UE工具窗口,支持众多控件类型

![Editing](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/Editing.gif)


## 安装和使用
### 程序工程
1, 拷贝Plugin目录下的TAPython目录到客户端工程的Plugin目录下，并编译

2, 拷贝TA/TAPython 目录到工程下

3, Editor Setting 中指定Python目录

### 美术工程

1, 拷贝TA/TAPython 目录到工程下，

2, Editor Setting 中指定Python目录到工程TA/TAPython/Python 目录下

### 选项

首次运行后会在工程目录下创建配置文件，
该文件为工具配置文件，其中的配置项如下：

TA\TAPython\Config\config.ini

        [Settings]
        MenuConfigFilePath=/TA/TAPython/UI/MenuConfig.json
        ChameleonDataFolder=/Game/TA/ChameleonTools
        
        [Advanced]
        MainbarExtensionHookName=Game
  	    MainMenuExtensionHookName=WindowLayout
        MenusOnToolbarEnabled=True
        SketchToolsEnabled=True
	
- MenuConfigFilePath: 工具配置文件的总入口
- ChameleonDataFolder: ChameleonDefaultData 工具数据蓝图文件
- MainbarExtensionHookName: 主工具栏图标位置
- MainMenuExtensionHookName: 主菜单项创建的位置
- MenusOnToolbarEnabled=True: 是否显示主工具栏上的菜单项
- SketchToolsEnabled=True:	是否启用Sketch工具，该工具可随着Json文件修改的同时自动刷新界面。用于快速编写和预览界面



## 功能一： 创建菜单项
该功能可以在ContentBrower，主菜单，工具栏等处添加菜单项。默认配置文件路径为上文中提到的/TA/TAPython/UI/MenuConfig.json，配置并修改该文件即可创建菜单项
![MenuOnToolBar.png](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/MenuOnToolBar.png)

Example：
MenuConfig_Example.json 节选

    {
        "OnSelectFolderMenu":
        {
            "name:": "Python Menu OnSelectFolderMenu",
            "items":
            [
                {
                    "name": "直接运行command中的python代码",
                    "command": "print 'run py code here'"
                },
                {
                    "name": "一个隐藏菜单，Enabled: false",
                    "command": "print 'run py code here'",
                    "Enabled": false
                },
                {
                    "name": "调用.py 文件中的函数",
                    "command": "import exampleEntry; exampleEntry.do_some_thing()",
                    "args": ""
                },
                {
                    "name": "把选中的文件夹路径当作参数传给python",
                    "command": "import exampleEntry; exampleEntry.do_some_with_this_folder(%paths)",
                    "needPaths": true
                },
                {
                    "name": "菜单中配置函数参数",
                    "command": "import exampleEntry; exampleEntry.test_params(%intArgs, %floatArgs, %strArgs)",
                    "intArgs": ["10", "14"],
                    "floatArgs": [1.1, 1.2],
                    "strArgs": ["Str A", "Str B", "Str C"]
                },
    
                {
                    "name": "子菜单",
                    "items":
                    [
                        {
                            "name": "这是子菜单",
                            "command": "print ('item in sub menu')"
                        },
                        {
                            "name": "子菜单下的子菜单",
                            "items":
                            [
                                {
                                    "name": "对目录中的资源做某些操作",
                                    "command": "print('Python leaf call.')"
                                }
                            ]
                        }
                    ]
                }
            ]
        }
        "OnSelectAssetsMenu":
        {
        },
        "OnMainMenu":
        {
        },
        "OnToolbar":
        {
        },
	    "OnToolBarChameleon": 
        {
            "name": "Python Chameleon on toolbar",
            "items": [
            {
                "name": "Chameleon Widget Gallery 控件示例",
                "ChameleonTools": "../Python/ChameleonGallery/ChameleonGallery.json"
            },
            {
                "name": "导出工具",
                "items": [
                    {
                        "name": "副本草图导出工具",
                        "ChameleonTools": "../Python/GrassMapDataExporter/GrassMapExporter.json",
                        "enabled": true
                    }
                ]
            }
        }
    }

### 参数说明
**"OnSelectFolderMenu":** ContentBrower中选中目录，或点击空白区域时右键菜单入口

**"OnSelectAssetsMenu":** ContentBrower中选中资源时右键菜单入口

**"OnMainMenu":** 主菜单中的菜单项入口

**"OnToolbar":** 主工具栏菜单入口，图标为Python

**"OnToolBarChameleon"**: Chameleon Tools 工具入口, 图标为绿色变色龙

**"items"**: Array 类型，其中的各元素为子菜单项，可嵌套成树状

**"name":** 菜单项显示名

**"command":** 绑定到菜单项的python代码，支持import文件，并调用其中的函数

**"enabled":** 是否启用该菜单项，设置为false时会隐藏该菜单项

**"ChameleonTools"**: 值为点击该菜单项打开的ChameleonTools工具的UI json文件，下文述



## 功能二： 创建编辑器UI

该功能可以根据UI文件（.json）动态创建使用原生Slate代码的UE4编辑器界面。并将界面于Python工具代码绑定，实现数据的双向互通。无需编译，可实时预览。



### 支持的控件
- SBox
- SBorder
- SVerticalBox
- SHorizontalBox
- STextBlock
- SScrollBox
- SGridPanel
- SButton
- SCheckBox
- SSpinBox
- SSeparator
- SHeader
- SEditableText
- SEditableTextBox
- SMultiLineEditableText
- SMultiLineEditableTextBox
- SComboBox
- SListView
- SHeaderRow
- SImage
- SSpacer
- SBreadcrumbTrail
- SSearchBox
- SHyperlink
- SThrobber
- SSlider
- SProgressBar

#### Chameleon Gallery

![ChameleonGallery2](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/ChameleonGallery2.png)

具体链接：


### Chameleon Tools 入口

MenuConfig_Example.json 中的 OnToolBarChameleon项，支持子菜单

    {
	    "OnToolBarChameleon": 
        {
            "name": "Python Chameleon on toolbar",
            "items": [
            {
                "name": "Chameleon Widget Gallery 控件示例",
                "ChameleonTools": "../Python/ChameleonGallery/ChameleonGallery.json"
            },
			{
				"name": "Chameleon tools 最小范例",
				"ChameleonTools": "../Python/Example/ChameleonExample.json"
			},
            {
                "name": "导出工具",
                "items": [
                    {
                        "name": "副本草图导出工具",
                        "ChameleonTools": "../Python/GrassMapDataExporter/GrassMapExporter.json",
                        "enabled": true
                    }
                ]
            }
        }
    }


### ChameleonTools 最小范例
以上文中的"ChameleonTools": "../Python/Example/ChameleonExample.json" 为例

![AMinimumTool](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/AMinimumTool.gif)

ChameleonExample.json
	
    {
        "ChameleonData": "",
        "TabLabel": "Example",
        "InitTabSize": [130, 100],
        "InitTabPosition": [50, 100],
        "InitPyCmd": "import Example; thisExample = Example.ChameleonExample.ChameleonExample(%JsonPath)",
        "Root":
        {
            "SVerticalBox":
            {
                "Slots": [
                    {
                        "SButton": {
                            "Text": "Click Me",
                            "HAlign": "Center",
                            "VAlign": "Center",
                            "OnClick": "thisExample.on_button_click()"
                        }
                    },
                    {
                        "SEditableTextBox":
                        {
                            "IsReadOnly": true,
                            "Aka": "InfoOutput",
                            "Text": ""
                        }
                    }
                ]
            }
        }
    }
	
ChameleonExample.py

    # -*- coding: utf-8 -*-
    import unreal
    from Utilities.Utils import Singleton
    
    class ChameleonExample():
        __metaclass__ = Singleton
        def __init__(self, jsonPath):
            self.jsonPath = jsonPath
            self.data = unreal.PythonBPLib.get_chameleon_data(self.jsonPath)
            self.clickCount = 0
            self.ui_output = "InfoOutput"
    
        def on_button_click(self):
            self.clickCount += 1
            self.data.set_text(self.ui_output, "Clicked {} times".format(self.clickCount))
	
#### ChameleonExample.json 参数说明
**ChameleonData**: 工具数据蓝图文件路径，可缺省为空或不配置，缺省时会使用默认数据蓝图。例如: "/Game/TA/ChameleonTools/PyModelRenderer"

**TabLabel**: 工具页签名

**InitPyCmd**: 该工具初始化时调用的Python代码。通常为导包和创建Python工具单例并将其赋予变量，以便后续控件调用

**InitTabSize**: 用于控制工具Tab尺寸，可以缺省，缺省时工具界面尺寸为ue默认NomadTab的尺寸

**InitTabPosition**: 用于控制工具默认出现位置

**Root**: 其中的内容为创建Slate界面的伪Slate代码

注：ChameleonData 为Python 和Slate交换数据的中间载体，是UChameleonData类型的蓝图子类，默认不配置和忽略。如对单个工具有配置资源的需求，又不适合该python代码，可将此类设置配置在该蓝图子类的实例asset上。（新建一个蓝图子类，添加Public的UProperty）

#### 界面控件与Python代码的互通

1 界面的Python工具类，需要继承 Utilities.Utils中的Singleton。并在构造函数获取传入的Json文件的路径。该路径会作为该工具的唯一标识符，用于获取该工具的ChameleonData实例

2 ChameleonExample.json在工具界面被创建时将运行"InitPyCmd"中的代码，完成Python工具实例的创建，并持有该实例的引用

3 Button控件被点击时，会运行OnClick中的Python函数，并通过步骤2中持有的引用，调用Python工具中的函数on_button_click

4 on_button_click 会通过self.data（也就是ChameleonData的实例中）的方法，修改ui界面中的内容，显示反馈信息






### C++ Slate链式编程语法转Json Slate的方法

1、省略SNew，直接写控件名，SAssignNew(ButtonPicture, SImage); 转换成"SImage":{"Aka": "ButtonPicture"}

2、 Slate中支持单个子组件的Widget中的[]转换成 "Content"：\{ }

2、支持多个Slots的Widget中的 \+ SXXXX::Slot  转换成 "Slots": [\{ }], 每个Slot为Slots数组中的一个JsonValue

3 从Style中获取Brush的写法，转换成Style和Brush两个值

4 Vector2, Vector4 转换成数组形式 如[1,2,3,4]


5 其他具体可参见 http://confluence.oa.zulong.com/display/EngineHub/Chameleon+Gallery 中的示例或实际应用

例

    SNew(SBorder)
    .BorderImage(FEditorStyle::Get().GetBrush("ToolPanel.DarkGroupBorder"))
    [
        SNew(SSpacer)
        .Size(FVector2D(100, 50))
    ]
转换成
	
	"SBorder":{
        "BorderImage":
        {
            "Style": "FEditorStyle",
            "Brush": "ToolPanel.DarkGroupBorder"
        },
        "Content": {
            "SSpacer": {
                "Size": [100, 50]
            }
        }
    }




### ChameleonSketch 界面草稿工具
该工具用于创建界面时快速预览界面参数和效果，入口为图标，图

![Editing2](https://raw.githubusercontent.com/cgerchenhp/UE4_Python_Tools_Doc/master/Images/Editing2.gif)

用法：

点击该图标后，会弹出界面，直接修改ChameleonSketch.json文件中的内容，该界面会动态更新，待界面满意后，可以将该json文件中的内容拷贝到对应工具文件的json文件中

ps. 其他ChameleonTools的json文件，在点击按钮时加载和刷新，亦无需重启编辑器


### ChameleonData设置界面内容的接口
以下函数常被用于在Python代码中获取、修改界面中的特定组件的值。具体在ChameleonData.h中


			
