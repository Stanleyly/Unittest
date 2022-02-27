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

# 编写Unittest(2)

+ 例子：

person.py
```python
class Person(object):
	def __init__(self, name):
		self.name = name
	def get_name(self):
		"""获取姓名"""
		return self.name
```
company.py
```python
class Company(object):
 	def __init__(self, name, boss):
		self.name = name
		self.boss = boss
		self.staffs = set()
		
	def who_is_boss(self):
		"""老板是谁"""
		return boss.get_name()
		
	def hire(self.person):
		"""雇佣新员工"""
		.......
		
	def fire(self.person):
		"""解雇员工"""
		......
```
+ 单元测试的测试点
	+ who_is_boss()正确返回老板姓名
	+ 雇佣不同名的人，员工数+1
	+ 雇佣同名的人，员工数不变
	+ 解雇员工，员工数-1
	+ 解雇陌生人，员工数不变 

+ 针对测试点的单元测试代码
```python
import Unittest
import person
import company

class CompanyTestCase(unittest.TestCase):
	@classmethod
	def setUpClass(self):
		self.boss = person.Person("Zhang San")
		self.kfc = company.Company("KFC", self.boss)
		
	def tearDown(self):
		self.kfc.staffs.clear()
		
	def test_who_is_boss(self):
		"""获取公司老板的姓名"""
		self.assertEqual(self.kfc.who_is_boss(), "Zhang San")
		
	def test_number_of_staffs_increase_when_hire_different_name_person(self):
		"""雇佣新人，员工数增加"""
		self.kfc.hire(person.Person("Li Si"))
		self.assertEqual(len(self.kfc.staffs), 1)
		self.kfc.hire(person.Person("Hong Wei"))
		self.assertEqual(len(self.kfc.staffs), 2)
		
	def test_number_of_staffs_not_changer_when_hire_same_name_person(self):
		"""雇佣相同的人，员工数不增加"""
		self.kfc.hire(person.Person("Hong Wei")
		self.assertEqual(len(self.kfc.staffs), 2)
		self.kfc.hire(person.Person("Wang Wu"))
		self.assertEqual(len(self.kfc.staffs), 2)
		

```

# 运行Unittest
+ 运行全部用例
```python
if __name__=='__main__':
	unittest_main()
```
+ 运行测试集的用例
```python
def MyTestSuite():
	"""构造测试集"""
	suite = unittest.TestSuite()
	suite.addTest(PersonTestCase("test_get_name")
	suite.addTest(CompanyTestCase("test_who_is_boss"))
	return suite

if __name__='__main__':
	unittest.main(defaultTest='MyTestSuite')
```
