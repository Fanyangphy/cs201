# Assignment #1: 拉齐大家Python水平

Updated 0940 GMT+8 Feb 19, 2024

2023 fall, Complied by 杨帆，物理学院



**说明：**

1）数算课程的先修课是计概，由于计概学习中可能使用了不同的编程语言，而数算课程要求Python语言，因此第一周作业练习Python编程。如果有同学坚持使用C/C++，也可以，但是建议也要会Python语言。

2）请把每个题目解题思路（可选），源码Python, 或者C++（已经在Codeforces/Openjudge上AC），截图（包含Accepted），填写到下面作业模版中（推荐使用 typora https://typoraio.cn ，或者用word）。AC 或者没有AC，都请标上每个题目大致花费时间。

3）课程网站是Canvas平台, https://pku.instructure.com, 学校通知3月1日导入选课名单后启用。**作业写好后，保留在自己手中，待3月1日提交。**

提交时候先提交pdf文件，再把md或者doc文件上传到右侧“作业评论”。Canvas需要有同学清晰头像、提交文件有pdf、"作业评论"区有上传的md或者doc附件。

4）如果不能在截止前提交作业，请写明原因。



**编程环境**

==（请改为同学的操作系统、编程环境等）==

操作系统：macOS Ventura 13.4.1 (c)

Python编程环境：Spyder IDE 5.2.2, PyCharm 2023.1.4 (Professional Edition)

C/C++编程环境：Mac terminal vi (version 9.0.1424), g++/gcc (Apple clang version 14.0.3, clang-1403.0.22.14.1)



## 1. 题目

### 20742: 泰波拿契數

http://cs101.openjudge.cn/practice/20742/



思路：数组



##### 代码

```python
a=[0,1,1]
l=2
n=int(input())
if n<=2:
    print(a[n])
else:
    for i in range(n-2):
        a.append(a[-1]+a[-2]+a[-3])
    print(a[n])
```



代码运行截图 

<img src="C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219160435945.png" alt="image-20240219160435945" style="zoom:70%;" />





### 58A. Chat room

greedy/strings, 1000, http://codeforces.com/problemset/problem/58/A



思路：判断



##### 代码

```python
a=input()
b='hello'
t,k=0,False
for i in range(len(a)):
    if a[i]==b[t]:
        t+=1
    if t==5:
        k=True
        break
if k:
    print("YES")
else:
    print("NO")
```



代码运行截图

![image-20240219160546066](C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219160546066.png)





### 118A. String Task

implementation/strings, 1000, http://codeforces.com/problemset/problem/118/A



思路：字符串



##### 代码

```python
vowel=['a','e','i','o','u','y']
a=input()
b=[]
for i in range(len(a)):
    if a[i].lower() not in vowel:
        b.append(a[i].lower())
for i in range(len(b)):
    print('.'+b[i],end='')
```



代码运行截图

![image-20240219160622872](C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219160622872.png)





### 22359: Goldbach Conjecture

http://cs101.openjudge.cn/practice/22359/



思路：素数判断，另外有多种分解似乎没考虑到？（也有可能是我写错了



##### 代码

```python
a=[0,0]+[1]*10000
n=int(input())
for i in range(2,10000):
    if a[i]:
        for j in range(i*i,n+1,i):
            a[j]=0
for i in range(2,n):
    if a[i] and a[n-i]:
        print(i,n-i)
        break 
```



代码运行截图

<img src="C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219160934487.png" alt="image-20240219160934487" style="zoom:67%;" />





### 23563: 多项式时间复杂度

http://cs101.openjudge.cn/practice/23563/



思路：最大值



##### 代码

```python
a=list(map(str,input().split('+')))
max=0
for item in a:
    x,y=item.split('^')
    if (len(x)==1 or int(x[:len(x)-1])!=0) and int(y)>=max:
        max=int(y)
print(x[len(x)-1]+'^'+str(max))
```



代码运行截图

<img src="C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219161010269.png" alt="image-20240219161010269" style="zoom:67%;" />





### 24684: 直播计票

http://cs101.openjudge.cn/practice/24684/



思路：桶排序，找最大值



##### 代码

```python
a=[0]*100001
for item in map(int,input().split()):
    a[item]+=1
m=max(a)
for i in range(100001):
    if a[i]==m:
        print(i,end=' ')
```



代码运行截图 

<img src="C:\Users\FanYa\AppData\Roaming\Typora\typora-user-images\image-20240219161440735.png" alt="image-20240219161440735" style="zoom:67%;" />





## 2. 学习总结和收获

学习树的类写法，创建github!





