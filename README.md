## opencv 4.5.2 官方文档中文翻译版
###### Doxygen HTML 版本 https://docs.opencv.org/4.5.2/ 
###### 机器翻译加人工修正， 一边翻译一边更新。 
###### 内容仅供参考。

### 本来是要开通Gitee Pages服务的,貌似开不了了现在

可以下载回来 双击打开 index.html 一样可以正常使用该中文文档。
因为他是静态的不需要服务

试下这个把原来的博客干掉了
http://zhengshizeng.gitee.io/
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

翻译完成时替换文中的中文符号为英文(个人习惯)
F:\html-i18n-cli-master\lib\translate.js  35行
```
        var tempstr=await fanyi(origin, options.to)
        tempstr=tempstr.replace(/\：/g,":");
        tempstr=tempstr.replace(/\。/g,":");
        tempstr=tempstr.replace(/\（/g,"(");
        tempstr=tempstr.replace(/\）/g,")"); 
        tempstr=tempstr.replace(/\，/g,",");
        current.local=tempstr;
```