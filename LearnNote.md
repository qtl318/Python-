1. for _ in range(20): #_ 是个临时变量, 循环不使用的
2. tuple 元组,是一个不可变的列表适合用于多线程多进程安全任务，而且元组创建时间和所占空间都比列表省;
3. 每个内置函数都会有一些参数，可以调整函数功能，如：sorted(list1, ...reverse = True//key = len), print('\r', end = "", fulse=True)
4. round() 方法返回浮点数x的四舍五入值。
5. Pygame模块 
  pygame.display.init()  —  初始化 display 模块
  pygame.display.quit()  —  结束 display 模块
  pygame.display.get_init()  —  如果 display 模块已经初始化，返回 True
  pygame.display.set_mode()  —  初始化一个准备显示的窗口或屏幕
  pygame.display.get_surface()  —  获取当前显示的 Surface 对象
  pygame.display.flip()  —  更新整个待显示的  Surface 对象到屏幕上
  pygame.display.update()  —  更新部分软件界面显示
6. turtle模块绘图/tqdm
7. nonlocal 可以对父级作用域的变量进行修改,并且在当前作用域创建
8. dis模块主要是用来分析字节码的一个内置模块，经常会用到的方法是dis.dis([bytesource])，参数为一个代码块，可以得到这个代码块对应的字节码指令序列。
9. format格式：
#字符串
print('hello {0} i am {1}'.format('world','python'))   
# 输出结果：hello world i am python

print('hello {} i am {}'.format('world','python') )
# 输出结果：hello world i am python

print('hello {0} i am {1} . a now language-- {1}'.format('world','python')
# 输出结果：hello world i am python . a now language-- python

#字典
关键字参数
关键字参数值要对得上，可用字典当关键字参数传入值，字典前加**即可

site = {"name": "PC", "url": "www.XX.com", "com":"8888"}
print("网站名：{name}, 地址 {url}, 端口 {com}".format(**site))
# 输出结果：网站名：PC, 地址 www.XX.com, 端口 8888

args = [',', 'inx']
kwargs = {'obj': 'world', 'name': 'python'}
print('hello {obj} {} i am {name}'.format(*args, **kwargs))
# 输入结果：hello world , i am python

注意：魔法参数跟你函数中使用的性质是一样的：这里format(*args, **kwargs)) 等价于：format(‘,’,’inx’,obj = ‘world’,name = ‘python’)
