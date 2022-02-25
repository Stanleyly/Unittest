# 编写Unittest(2)

+ 例子：company.py
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
