---
layout: article
title:  "Python 类"
date:   2019-01-08 17:09:40 +0800
key: python-class-20190108
aside:
  toc: true
category: [Python, PythonFoundation]
---
*前导知识：（懂程序设计基础，面向对象程序设计更好）*  

## 一、 定义
类（class）封装了一组相关数据，并提供一系列方法对其维护；  
类之间的关系有继承（inhertiance，is-a）和组合（composition，has-a）；  
类和模块的区别：  
- 类可以生成多个实例；  
- 类可被继承和扩展；  
- 类实例的生命周期可控；  
- 类支持运算符，可按需重载；  
`没有意义的比较；也就是能帮助小白理解什么是类吧；不过如果是面试官问出这种问题，一时间，可能真的要卡住了；`{;.warning}  
建议将类与业务逻辑分离；业务逻辑与函数的概念更为吻合——过程化、无状态及用上下文传递数据；而类是以数据为中心，注重遗传，满足多实例需求；  

1. **创建**  
定义 Demo 类：  
```python
class Demo:
    pass
```

2. **名字空间**  
类都有自己的名字空间；子类不包括父类中的成员，需调用父类初始化方法 supper().__init__() 方法来引用父类类型（不是复制）；  


## 二、 字段

## 三、 属性

## 四、 方法

## 五、 继承

## 六、 开放类



## 附录
### 知识点
1.**函数内定义的类**  
放在函数内定义的类，每次调用函数都是新建，虽然名字和内容相同，但是也属于不同的类型；  

```python
def test():
    class Demo:
        pass
    return Demo()

a, b = test(), test()
print(a.__class__ is b.__class__) # False
```  
<span id="namespace">**2. 名字空间**</span>  


```python
class A:
    a = 100                 # 类字段

    def __init__(self, p):  # 实例初始化
        self.x = p          # 实例字段

    def get_x(self):        # 势力方法
        return self.x

class B(A):                 # 继承自 A
    b = "hello"

    def __init__(self, p, q):
        super().__init__(p) # 调用父类初始化方法
        self.y = q

    def get_y(self):
        return self.y

c = B(2, 3)

print("A:\n", A.__dict__)   # 类 A 的名字空间字典，不可直接修改
print("B:\n", B.__dict__)   # 类 B 的名字空间字典，不可直接修改
print("object c:\n", c.__dict__)    # 实例 c 的名字空间字典，可直接修改
print("dir(object c):\n", dir(c))   # 所有可访问的成员的名字
print("vars(object c):\n", vars(c)) # 和 __dict__ 功能一样
```
输出：  

```shell
A:
 {'__module__': '__main__', 'a': 100, '__init__': <function A.__init__>, 'get_x': <function A.get_x>, ...}
B:
 {'__module__': '__main__', 'b': 'hello', '__init__': <function B.__init__>, 'get_y': <function B.get_y>, ...}
object c:
 {'x': 2, 'y': 3}
dir(object c):
 ['a', 'b', 'get_x', 'get_y', 'x', 'y', ...]
vars(object c):
 {'x': 2, 'y': 3}
```
