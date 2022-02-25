# 编写Unittest(1)

+ 例子：person.py
```python
class Person(object):
	def __init__(self, name):
		self.name = name
	def get_name(self):
		"""获取姓名"""
		return self.name
```

+ 单元测试的测试点：get_name()正确返回姓名
+ 针对测试点的单元测试代码
```python 
import unittest
import person

Class PersonTest(unittest.TestCase):
	"""针对Person类的测试"""
	
	def setUp(self):
		self.p1 = person.Person("Zhang San")
		self.p2 = person.Person("Hongwei")
	
	def test_get_name(self):
		"""获取人的名字"""
		self.assertEqual(self.p1.get_name, 'Zhang San')
		self.assertEqual(self.p2.get_name, 'Hongwei')

```
