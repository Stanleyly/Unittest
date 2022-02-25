# Unittest 单元测试
* [1 什么是单元测试](#1-什么是单元测试)
* [2 单元测试的意义](#2-单元测试的意义)
* [3 单元测试框架选择](#3-单元测试框架选择)
* [4 Unittest基础概念](#4-Unittest基础概念)

## 1 什么是单元测试
+ 通常而言，一个单元测试用例是用于判断某个**特定条件或场景**下某个**特殊函数**的行为
+ 直观解释：我们针对一个函数，构造不同的输入，验证函数的输出是否符合预期

## 2 单元测试的意义
+ 针对质量
	- 测试针对性强，BUG更容易暴露
	- 场景构造简单，核心功能验证更充分
	- 保证代码结构良好，具有较高的可测性和可维护性
+ 针对效率
	- 测试场景构造快捷，减少调试时间
	- 只针对修改的代码展开测试，减少测试时间
	- 更多BUG在项目早期发现，缩短开发周期

## 3 单元测试框架选择
+ Unittest/PyUnit
	- Python标准库
	- 原生自带，无兼容性问题，其他框架的基础
	- 代码有些反锁，入门门槛稍高
+ Pytest
	- https://pypi.org/project/pytest/
	- 编码简洁，生态好，插件丰富
	- 第三方，需要安装

+ Nose2
	- https://pyqi.org/project/nose2/
	- 兼容unittest
	- 第三方，需要安装，迭代缓慢，用的人少

## 4 Unittest基础概念
+ Test（测试用例）：针对一个特定场景、特定目的的具体测试过程
+ TestCase（测试类）：可以包含同一个测试对象的多个测试用例
+ TestSuite（测试集）：可以包含多个测试类的多个测试用例
+ Assertion（断言）：必须使用断言判断测试结果
+ TestFixture：为测试做统一的准备和清除工作，通常是初始化、连接数据库、准备数据、断开数据库、清理现场等