```python
def extendlist(val, ll=[]): 
    ll.append(val)
    return ll


list1 = extendlist(10) 
list2 = extendlist(123, []) 
list3 = extendlist('a')

# list1 : [10, 'a']
# list2 : [123]
# list3 : [10, 'a']
# 新的默认列表只在函数被定义的那一刻创建一次。
# 调用时,若指定参数,使用指定参数
# 若不指定参数,使用函数定义时创建的对象
# 当 extendList 被没有指定特定参数 list 调用时，这组 list 的值 随后将被使用。这是因为带有默认参数的表达式在函数被定义的时候被计算，不是在调用的时候被计算。
```