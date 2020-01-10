---
layout: article
title:  "「Python」 xml.etree.ElementTree"
date:   2019-01-28 10:07:40 +0800
key: xml-etree-elementTree-20190128
aside:
  toc: true
category: [software, python, pystl]
---
<span id='head'></span>  

> Python 3.5.6 官方文档：<https://docs.python.org/3.5/library/xml.etree.elementtree.html>  

# 1 API

| [parse]() | [iter]() | [findall]() | []() |
| --- | --- | --- | --- |
| [start]() | [end]() | [close]() | [data]() |
| [XML]() | [XMLID]() | [Element]() | [SubElement]() |
| [Comment]() | [tostring]() | [extend]() | [write]() |


# 2 读
[示例](#read)



# 3 写


-------------------  
[End](#head)
{:.warning}  

# 附录
## A API


## B 示例
<span id='read'>**1. 读取 xml 文件**</span>
```python
import xml.etree.ElementTree as ET
def read(file):
    tree = ET.parse(file)
    root = tree.getroot()

    NAME, SUB_NAME = 'VIDEO', 'file'
    file_node = root.find(NAME).find(SUB_NAME)
    name = file_node.text.strip('"')

    data = []
    NAME_RECURSIVE, NAME_ITEM = 'action', 'id'
    node_recursive = root.findall(NAME_RECURSIVE)
    for node in node_recursive:
        id = int(float(node.find(NAME_ITEM).text))
        data.append(id)
```

## C 推荐资料


## D 参考文献
1. Doug Hellmann 著, 苏金国, et al 译. Python3 标准库[M]. 北京:机械工业出版社, 2018.
