### SImage
#### 支持的参数

* ToolTipText
* Visibility

Example 1:
    "SImage": 
	{
    	"Aka": "ImgGrassMap"
    }
    
#### 注意事项
Aka SImage控键在工具中的变量名，类似与SAssignNew(ImgGrassMap, SImage)



#### Python中设置界面的接口函数

**set_image_data**

设置SImage组件的Brush内容，参数是uint8

py help:
				
    set_image_data(...)
        x.set_image_data(aka_name, raw_data, width, height) -> None
        Set Image Data
        
        Args:
            aka_name (Name): 
            raw_data (Array(uint8)): 
            width (int32): 
            height (int32):
			
**set_image_pixels**
			
设置SImage组件的Brush内容

py help:

    set_image_pixels(...)
        x.set_image_pixels(aka_name, pixel_colors, width, height) -> None
        Set Image Pixels
        
        Args:
            aka_name (Name): 
            pixel_colors (Array(LinearColor)): 
            width (int32): 
            height (int32):