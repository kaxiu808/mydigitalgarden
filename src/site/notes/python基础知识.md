---
{"dg-publish":true,"dp-python":true,"permalink":"/python基础知识/","dgPassFrontmatter":true}
---



怎么理解  异步  -- [[异步爬虫案例\|异步爬虫案例]]

关于playwright 是一个用于自动化浏览器操作的开源工具
可以通过python编写程序，所编写的这组程序可以指定的进行一系列，基于浏览器所触发的动作。



## 类的知识点

```python
# class student(object):  
#     students = []  
#  
#     def add_stu(self):  
#         print("添加学生")  
#  
#     def del_stu(self):  
#         print("删除学生")  
#  
#     def update_stu(self):  
#         print("更新学生")  
#  
#     def show_stu(self):  
#         print("展示学生")  
#  
#  
# class customer():  
#     customer = []  
#  
#     def add_customer(self):  
#         print("添加客户")  
#  
#     def del_customer(self):  
#         print("删除客户")  
#  
#     def update_customer(self):  
#         print("更新客户")  
#  
#     def show_customer(self):  
#         print("展示客户")  
#  
  
  
  
  
  
  
#  版本2: 类  
#  
# class Dog():  
#     # 属性： 数据  
#     # 行为：方法  
#     leg_num = 4  
#     has_hair = True  
#  
#     def bark(self):  
#         print("狂吠")  
#  
#     def kenGuTou(self):  
#         print("啃骨头")  
#  
# alex = Dog()  
# print(alex.leg_num)  
# print(alex.has_hair)  
  
  
  
# peiQi = Dog()  
# print(peiQi.leg_num)  
# print(peiQi.has_hair)  
  
# l  = [23,45,67,323,12,7]  
# # print([i**2 for i in l])  
#  
# def foo(item):  
#     return item ** 2  
# print(list(map(foo,l)))  
  
  
# print(list(map(lambda item:item**2,l))) #[529, 2025, 4489, 104329, 144, 49]  
  
  
  
# l  = [23,45,67,323,12,7]  
#  
# for i in l:  
#     if i % 2 != 0:  
#         l.remove(i)  
# print(l)  
  
  
# l2 = []  
# for i in l:  
#     if i % 2 == 0:  
#         l2.append(i)  
#  
# print(l2)  
  
  
  
  
  
# l  = [23,45,67,323,12,7]  
# # print(list(filter(lambda i:False,l)))  
# print(list(filter(lambda i:i%2==0,l)))  
  
  
  
person_list = [  
    {"name":"yuan","gfs":["高圆圆","刘亦菲"]},  
    {"name":"rain","gfs":["高圆圆","刘亦菲","赵丽颖"]},  
    {"name":"alex","gfs":["米尔儿"]}  
]  
  
print(list(filter(lambda item:len(item.get('gfs'))>=2,person_list)))
```