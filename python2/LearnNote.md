# learn.md
学习笔记-menglei

## 学习的顺序(与源程序相同)

---------------
`2017.8.21 16:11`
## about_asserts


* Python yield 使用浅析
https://www.ibm.com/developerworks/cn/opensource/os-cn-python-yield/

* isinstance
http://blog.csdn.net/business122/article/details/7608176

```txt
isinstance(object, classinfo)   
判断实例是否是这个类或者object是变量  

classinfo 是类型(tuple,dict,int,float)  
判断变量是否是这个类型   

class objA:   
pass   

A = objA()   
B = 'a','v'   
C = 'a string'   

print isinstance(A, objA)   
print isinstance(B, tuple)   
print isinstance(C, basestring)   
输出结果：   
True   
True   
True  
```

## about_strings

* 下面的字符串是相同的

```py
a = "He said, \"Don't\""
b = 'He said, "Don\'t"'
```
```py
string = r"Konnichi wa, world!" # !!! 这个也是字符串类型
self.assertEqual(True, isinstance(string, basestring))
```
```py
a = "Hello \"world\"."
b = """Hello "world"."""
self.assertEqual(True, (a == b))
```
```py
string = """Hello "world\""""
self.assertEqual("Hello \"world\"", string)
```
```py
string = "Hello" ", " "world"
self.assertEqual("Hello, world", string)
```
```py
def test_plus_equals_also_leaves_original_string_unmodified(self):
    original = "Hello, "
    hi = original
    there = "world"
    hi += there   # += 不会修改原始字符串的值
    self.assertEqual("Hello, ", original)
```
```py
string = "\n"
self.assertEqual(1, len(string))
```

## about_none

```py
self.assertEqual(True, isinstance(None, object))
self.assertEqual(True, None is not 0)
self.assertEqual(True, None is None)
self.assertEqual(True, None is not False)
```

* python 中的is

```py
# is判断的是a对象是否就是b对象，是通过id来判断的
# ==判断的是a对象的值是否和b对象的值相等，是通过value来判断的
>>> a = 1
>>> b = 1.0
>>> a is b
False
>>> a == b
True
>>> id(a)
12777000
>>> id(b)
14986000
>>> a = 1
>>> b = 1
>>> a is b
True
>>> a == b
True
>>> id(a)
12777000
>>> id(b)
12777000
```

`2017.8.22 19:09`
### about_list
```py
nums = list()
self.assertEqual([], nums)
```
```py
noms = ['peanut', 'butter', 'and', 'jelly']

self.assertEqual(['peanut'], noms[0:1])
self.assertEqual(['peanut', 'butter'], noms[0:2])
self.assertEqual([], noms[2:2])
self.assertEqual(['and', 'jelly'], noms[2:20])########
self.assertEqual([], noms[4:0])
self.assertEqual([], noms[4:100])########
self.assertEqual([], noms[5:0])

self.assertEqual(['and', 'jelly'], noms[2:])
self.assertEqual(['peanut', 'butter',], noms[:2]) ########
```

`2017.8.23 10:28`
### about_list_assignments

### about_dictionaries  字典

```py
empty_dict = dict()
self.assertEqual(dict, type(empty_dict))
self.assertEqual(dict(), empty_dict)
self.assertEqual(0, len(empty_dict))  # len is 0
```

```py
dict1 = {'one': 'uno', 'two': 'dos'}
dict2 = {'two': 'dos', 'one': 'uno'}

self.assertEqual(True, dict1 == dict2)
```

### about_string_manipulation
> 其他string 相关函数

```py
string = "Bacon, lettuce and tomato"
self.assertEqual("let", string[7:10]) # 忽略掉空格
len(string) == 26
```
```py
string = r'\n'   # raw string
self.assertNotEqual('\n', string)
self.assertEqual("\\n", string)
self.assertEqual(2, len(string))
```

### about_tuples

### about_methods
