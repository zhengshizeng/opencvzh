## opencv 4.5.2 �ٷ��ĵ����ķ����
###### Doxygen HTML �汾 https://docs.opencv.org/4.5.2/ 
###### ����������˹������� һ�߷���һ�߸��¡� 
###### ���ݽ����ο���

### ������Ҫ��ͨGitee Pages�����,ò�ƿ�����������

�������ػ��� ˫���� index.html һ����������ʹ�ø������ĵ���
��Ϊ���Ǿ�̬�Ĳ���Ҫ����

���������ԭ���Ĳ��͸ɵ���
http://zhengshizeng.gitee.io/
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

�������ʱ�滻���е����ķ���ΪӢ��(����ϰ��)
F:\html-i18n-cli-master\lib\translate.js  35��
```
        var tempstr=await fanyi(origin, options.to)
        tempstr=tempstr.replace(/\��/g,":");
        tempstr=tempstr.replace(/\��/g,":");
        tempstr=tempstr.replace(/\��/g,"(");
        tempstr=tempstr.replace(/\��/g,")"); 
        tempstr=tempstr.replace(/\��/g,",");
        current.local=tempstr;
```