### SBreadcrumbTrail
#### 支持的参数
* Type
* OnCrumbClick
* ButtonContentPadding
* OnCrumbClick
* ToolTipText
* Visibility

Example 1:

    "SBreadcrumbTrail":
    {
        "Aka": "SBreadcrumbTrailA",
        "type": "string",
        "ButtonContentPadding": 1,
        "OnCrumbClick": "print(%)"
    }
      
#### 注意事项
type 目前支持 string

Aka(as know as) 的值为控件名，用于查找和获得控件，类似于与 SAssignNew(SBreadcrumbTrailA, SBreadcrumbTrail)。控件名需要在单个工具Json文件中唯一


#### Python中设置界面的接口函数

**push_breadcrumb_string**

为SBreadcrumbTrail Push一个string项

py help:
	
    push_breadcrumb_string(...)
        x.push_breadcrumb_string(aka_name, crumb_text, new_crumb_data) -> None
        Push Breadcrumb String
        
        Args:
            aka_name (Name): 
            crumb_text (str): 
            new_crumb_data (str):
    
**pop_breadcrumb_string**		

从SBreadcrumbTrail Pop出一个选项

py help:
	
    pop_breadcrumb_string(...)
        x.pop_breadcrumb_string(aka_name) -> str
        Pop Breadcrumb String
        
        Args:
            aka_name (Name): 
        
        Returns:
            str:

**clear_breadcrumbs_string**

清空SBreadcrumbTrail中的所有项

py help:
			
    clear_breadcrumbs_string(...)
        x.clear_breadcrumbs_string(aka_name, pop_all_crumbs_to_clear=False) -> None
        Clear Breadcrumbs String
        
        Args:
            aka_name (Name): 
            pop_all_crumbs_to_clear (bool):	

**get_breadcrumbs_count_string**	

获取SBreadcrumbTrail中的选项数量

py help:
	
    get_breadcrumbs_count_string(...)
        x.get_breadcrumbs_count_string(aka_name) -> int32
        Get Breadcrumbs Count String
        
        Args:
            aka_name (Name): 
        
        Returns:
            int32:
