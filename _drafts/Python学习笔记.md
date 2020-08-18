Python学习笔记
==========
## 了解Python ##
[Python官网](https://www.python.org/ "Python官网")
## 特点 ##
- 开源
- 简单明确
- 可嵌套，可扩展
- 解释型语言（运行期间才编译，运行效率低于编译型语言），天生具有平台移植性
- 广泛的标准库
- 代码无法加密
## python3安装turtle问题 ##
1. 手动下载安装[twisted](https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted)（直接安装因为版本不一样安装失败，所以手动下载），使用命令 pip install + 文件完整路径 安装
2. 手动下载[turtle](https://pypi.org/project/turtle/0.0.2/#files) ，解压到本地
3. 修改setup.py文件，将第40行为：except (ValueError, ve)（原来的是Python2的写法，没有括号，加了括号之后Python3就能用了。）
4. 使用命令 pip install -e + 解压路径 进行安装

## vs code 运行turtle模块代码报错##
    AttributeError: partially initialized module 'turtle' has no attribute 'pensize' (most likely due to a circular import)
文件名不能与turtle相同

## 基础数据类型 ##
- 整形
- 浮点型
- 字符串类型
- 布尔类型，True 或 False

## 变量命名规则 ##

- 以字母、数字和下划线构成，不能以数字开头
- 大小写敏感
- 不能使用关键字或者保留字命名

## 条件语句 ##
- 每个条件后面跟：，通过缩进来区分代码块
- 多条件语句可以使用  if ... elif ... else，也可以嵌套if ... 	else 语句

## 函数 ##
- def 定义函数
- 不支持函数重载，但可以通过可变参数实现重载效果
- 可以为参数设置默认值
- 通过关键字指定参数，可以忽略参数顺序、
- 收集参数，定义形参前加*，收集参数和普通参数同时定义时，使用普通参数可以设置默认值或者必须设置关键字
- 默认返回None对象
- 函数内修改全局变量，python会创建个和全局变量名一样的局部变量
- 内嵌函数，函数内定义函数
- nonlocal关键字声明不是一个局部变量
- lambda
- 递归，Python3最多支持100层

## 字符串 ##


## 集合set ##
- 不支持索引
- 集合里的元素是唯一的
- frozenset,不可变集合