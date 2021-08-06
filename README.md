## opencv 4.5.2 官方文档中文翻译版
###### Doxygen HTML 版本 https://docs.opencv.org/4.5.2/ 
###### 机器翻译加人工修正， 一边翻译一边更新。 
###### 内容仅供参考。




---

#####翻译工具
```
https://github.com/F-loat/html-i18n-cli#html-i18n-cli
```

### html-i18n-cli
> HTML 国际化工具

### 安装
```
npm i -g html-i18n-cli
```
### 使用
##### 生成 JSON 文件
```
html parse test.html
```
##### 翻译 JSON 文件,生成JOSN
输入两次 Ctrl + C 终止，机翻后可手动校对
```
html translate test.json
```
- -t zh 指定目标语言
- -n 50 指定更新频率   

##### 转换 HTML 文件到中文
```
html render test.html test.json
```
### 附加功能
##### JSON 转 EXCEL
```
html convert test.json
```
##### EXCEL 转 JSON
```
html convert test.xlsx
```


---
##### 工具源码修改

F:\html-i18n-cli-master\lib\utils\html2texts.js   
过滤掉这些属性   --不翻译(代码块不用翻译)
```
#10行增加下面
 const iscode = node.tag === 'code'
    if (isStyle || isScript ||iscode) return
    
    const isdev =node.tag==='div'
    const isa =node.tag==='a'
    if(isdev || isa)
    {
      const isfrag= node.attrs.class==='fragment'
      const isel= node.attrs.class==='el'
      if(isfrag || isel)
      {
        return 
      }  
      
    }
```

```
    if(node.tag==='address')
    {
      if(node.attrs.class==='footer')
      {
        return 
      }
    }
    if(node.tag==='tbody')
    {
      return 
    }
```

##### 批量翻译
```
写个批处理
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\annotated.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\classes.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\classcv_1_1detail_1_1GraphCutSeamFinderBase.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\classcv_1_1gapi_1_1onnx_1_1Params.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\structcv_1_1cudev_1_1numeric__limits_3_01short_01_4-members.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d04\structcv_1_1cudev_1_1less.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d05\group__cudaimgproc.json 
...

```
