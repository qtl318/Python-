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

10. 
filter(function, sequence)：对sequence中的item依次执行function(item)，将执行结果为True的item组成一个List/String/Tuple（取决于sequence的类型）。
map(function, sequence) ：对sequence中的item依次执行function(item)，将执行结果function(item)组成一个List返回。
reduce(function, sequence, starting_value)：对sequence中的item顺序迭代调用function，如果有starting_value，还可以作为初始值调用。function接收的参数个数只能为2，先把sequence中第一个值和第二个值当参数传给function，再把function的返回值和第三个值当参数传给function，然后只返回一个结果。

#1.lambda用法，冒号之前的是入参，冒号之后的是表达式，返回的值，最简单的函数
print [(lambda x:x*x)(x)for x in range(11)]
#结果：[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
print (lambda x:x*x)(3)
#结果：9
g=lambda x:x*x
print g(4)
#结果：16

#2.filter用法:返回执行结果为TRUE的入参（入参是列表字符元组）
print filter(lambda x:x*x-4,range(10))
#结果：[0, 1, 3, 4, 5, 6, 7, 8, 9]

def is_odd(n):
    return n % 2 == 1 
newlist = filter(is_odd, [1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print(newlist)


#3.map的用法：对列表入参依次执行函数。入参为列表，有多少个列表，就应该有多少个入参。
print map(lambda x:x*x-4,range(10))
#结果：[-4, -3, 0, 5, 12, 21, 32, 45, 60, 77]
print map(lambda x,y:x*y-4,range(3),[8,9,10])
#结果：[-4, 5, 16]

#4.reduce用法：先把sequence中第一个值和第二个值当参数传给function，再把function的返回值和第三个值当参数传给fuction,最终返回一个结果值
#接收的入参个数只能为2
print reduce(lambda x,y:x*y-4,range(4))
#结果：-40
#计算0到100的和
print reduce(lambda x,y:x+y, range(101))
#结果：5050
print reduce(lambda x,y:x+y, range(101),100)
#结果：5150

11. 参数的元信息，便于函数使用
def add(a:int, b:int) -> int:
	return a*b

print(add(3,5))

(help(add))
print(add.__annotations__)

12. 
