1) 核心类差异
1. Python3对Unicode字符的原生支持。
Python2 中使用 ASCII 码作为默认编码方式导致 string 有两种类型 str 和 unicode，Python3 只
支持 unicode 的 string。Python2 和 Python3 字节和字符对应关系为:

|   py2   | py3   |   表现 |   转换 |  作用 |
|  :---   | ---: | :---: | :---: | :---: |
| str     | bytes |   字节  | encode | 存储 |
| unicode | str   |  字符   | decode | 显示 |

2. Python3采用的是绝对路径的方式进行import。

Python2 中相对路径的 import 会导致标准库导入变得困难(想象一下，同一目录下有 file.py，如 何同时导入这个文件和标准库 file)。Python3 中这一点将被修改，如果还需要导入同一目录的文件必 须使用绝对路径，否则只能使用相关导入的方式来进行导入。

3. Python2中存在老式类和新式类的区别，Python3统一采用新式类。新式类声明要求继承object， 必须用新式类应用多重继承。

4. Python3 使用更加严格的缩进。Python2 的缩进机制中，1 个 tab 和 8 个 space 是等价的，所 以在缩进中可以同时允许 tab 和 space 在代码中共存。这种等价机制会导致部分 IDE 使用存在问题。 Python3 中 1 个 tab 只能找另外一个 tab 替代，因此 tab 和 space 共存会导致报错:TabError: inconsistent use of tabs and spaces in indentation.

2) 废弃类差异
1. print 语句被 Python3 废弃，统一使用 print 函数
2. exec 语句被 python3 废弃，统一使用 exec 函数
3. execfile 语句被 Python3 废弃，推荐使用 exec(open("./filename").read())
4. 不相等操作符"<>"被 Python3 废弃，统一使用"!="
5. long 整数类型被 Python3 废弃，统一使用 int
6. xrange 函数被 Python3 废弃，统一使用 range，Python3 中 range 的机制也进行修改并提高 了大数据集生成效率
7. Python3 中这些方法再不再返回 list 对象:dictionary 关联的 keys()、values()、items()，zip()， map()，filter()，但是可以通过 list 强行转换:

```python
mydict={"a":1,"b":2,"c":3}
mydict.keys() #<built-in method keys of dict object at 0x000000000040B4C8> 
list(mydict.keys()) #['a', 'c', 'b']
```
8. 迭代器 iterator 的 next()函数被 Python3 废弃，统一使用 next(iterator)
9. raw_input 函数被 Python3 废弃，统一使用 input 函数
10. 字典变量的 has_key 函数被 Python 废弃，统一使用 in 关键词
11. file 函数被 Python3 废弃，统一使用 open 来处理文件，可以通过 io.IOBase 检查文件类型 12. apply 函数被 Python3 废弃
13. 异常 StandardError 被 Python3 废弃，统一使用 Exception

3) 修改类差异
1. 浮点数除法操作符“/”和“//”的区别
“ / ”:
Python2:若为两个整形数进行运算，结果为整形，但若两个数中有一个为浮点数，则结果为 浮点数;
Python3:为真除法，运算结果不再根据参加运算的数的类型。
“//”: Python2:返回小于除法运算结果的最大整数;从类型上讲，与"/"运算符返回类型逻辑一致。 Python3:和 Python2 运算结果一样。
2. 异常抛出和捕捉机制区别 

Python2
```python
raise IOError, "file error" #抛出异常 
except NameError, err: #捕捉异常
```
Python3
```python
raise IOError("file error") #抛出异常
except NameError as err: #捕捉异常
```
3. for 循环中变量值区别
Python2，for 循环会修改外部相同名称变量的值
```python
i = 1
print('comprehension: ', [i for i in range(5)])
print ('after: i =', i ) #i=4
```
Python3，for 循环不会修改外部相同名称变量的值
```python
i = 1
print('comprehension: ', [i for i in range(5)])
print ('after: i =', i ) #i=1
```
4. round 函数返回值区别 
Python2，round 函数返回 float 类型值
```python
isinstance(round(15.5),int) #True
```
Python3，round 函数返回 int 类型值
```python
isinstance(round(15.5),float) #True
```
5. 比较操作符区别
Python2 中任意两个对象都可以比较
```python
11 < 'test' #True
```
Python3 中只有同一数据类型的对象可以比较
```python
11 < 'test' # TypeError: unorderable types: int() < str()
```
