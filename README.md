# week3
#1、input去重
list1 = eval(input('请输入列表list1：'))
list2 = list(set(list1))
print(list2)

#set函数可迭代对象对象，返回新的集合对象

list1 = eval(input('请输入列表list1：'))
list2=[]
for i in list1:
    if not i in list2:
        list2.append(i)
print(list2)


#2、根据demo文件创建demo_new文件
filename = 'demo.py'
with open(filename, 'r') as fp:
    lines = fp.readlines()
maxLength = len(max(lines, key=len))

lines = [line.rstrip().ljust(maxLength)+'#'+str(index)+'\n'
         for index, line in enumerate(lines)]
with open(filename[:-3]+'_new.py', 'w') as fp:
    fp.writelines( lines)
    
    
#3、输入一个列表，对偶数计数
def even_num(x):
    sum=0
    for i in x:
        if i%2==0:#i除以2取余数，余数为0，则i是2的倍数，为偶数
            sum+=1
    return sum

res=even_num(eval(input('请输入列表lst：')))
print(res)
#接收列表输入：lst = eval(input('请输入列表lst：'))

#4、冒泡排序
def bubble_sort(alist):
    for j in range(1,len(alist) - 1):
        count = 0
        for i in range (0,len(alist)-1-j):
            if alist[i] > alist[i + 1]:
                alist[i],alist[i + 1] = alist[i + 1],alist[i]
                count += 1
        if 0 == count:
            break

if __name__ == '__main__':
    li = [1, 2, 6, 0, 3, 2, 0.5, -1, 2.4]
    print('排序前: ',li)
    bubble_sort(li)
    print('排序后: ',li)
    
    
  #5、单词计数
import string

path = 'C:/Users/lenovo/Desktop/Walden.txt'
with open(path, 'r', encoding='utf-8') as text:
    # 1. 首先进行分词
    raw_words = text.read().split()

    # 2. 把每个单词首尾连在一起的符号去掉，大写字母统一成小写
    words_list = [word.strip(string.punctuation).lower() for word in raw_words]

    # 3. 数据结构转换成集合，这里重复的单词会被自动丢弃
    words_set = set(words_list)

    # 4. 创建字典键值对：key为单词，value为单词出现的频率
    words_dict = {keyword: words_list.count(keyword) for keyword in words_set}

    # 5、根据words_dict中value的值对字典进行排序输出
    # word是一个词条，word[0]是单词，word[1]是单词出现的频率

for word in sorted(words_dict.items(), key=lambda word: word[1], reverse=True):
    print('{}--{} times'.format(word[0], word[1]))
    
    #6、求sin面积
import math
n = 10
width =2*math.pi/n
a =[]
b =[]
    # 等分0~2*pi之间的区间端点值x
for i in range(n):
	a.append(i*width)
for i in a:
	b.append(abs(math.sin(i)))
area = sum(b)*width
print(area)
    # 列表推导式
s = [abs(math.sin(i*width))*width for i in range(n)]
print(s)




