## opencv 4.5.2 �ٷ��ĵ����ķ����
###### Doxygen HTML �汾 https://docs.opencv.org/4.5.2/ 
###### ����������˹������� һ�߷���һ�߸��¡� 
###### ���ݽ����ο���




---

#####���빤��
```
https://github.com/F-loat/html-i18n-cli#html-i18n-cli
```

### html-i18n-cli
> HTML ���ʻ�����

### ��װ
```
npm i -g html-i18n-cli
```
### ʹ��
##### ���� JSON �ļ�
```
html parse test.html
```
##### ���� JSON �ļ�,����JOSN
�������� Ctrl + C ��ֹ����������ֶ�У��
```
html translate test.json
```
- -t zh ָ��Ŀ������
- -n 50 ָ������Ƶ��   

##### ת�� HTML �ļ�������
```
html render test.html test.json
```
### ���ӹ���
##### JSON ת EXCEL
```
html convert test.json
```
##### EXCEL ת JSON
```
html convert test.xlsx
```


---
##### ����Դ���޸�

F:\html-i18n-cli-master\lib\utils\html2texts.js   
���˵���Щ����   --������(����鲻�÷���)
```
#10����������
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

##### ��������
```
д��������
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\annotated.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\classes.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\classcv_1_1detail_1_1GraphCutSeamFinderBase.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\classcv_1_1gapi_1_1onnx_1_1Params.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d03\structcv_1_1cudev_1_1numeric__limits_3_01short_01_4-members.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d04\structcv_1_1cudev_1_1less.json 
node F:\html-i18n-cli-master\bin\html.js translate work\opencvzh\opencvzh\d0\d05\group__cudaimgproc.json 
...

```
