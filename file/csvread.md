# CSV文件



CSV文件：Comma-Separated Values，中文叫逗号分隔值或者字符分割值，其文件**以纯文本的形式存储表格数据。**可以把它理解为一个表格，只不过这个表格是以纯文本的形式显示的，单元格与单元格之间，默认使用逗号进行分隔；每行数据之间，使用换行进行分隔。

```
name,age,score
zhangsan,18,98
lisi,20,99
wangwu,17,90
jerry,19,95
```



Python中的csv模块，提供了相应的函数，可以让我们很方便的读写csv文件。

### CSV文件的写入

```python
import csv

# 以写入方式打开一个csv文件
file = open('test.csv','w')

# 调用writer方法，传入csv文件对象，得到的结果是一个CSVWriter对象
writer = csv.writer(file)

# 调用CSVWriter对象的writerow方法，一行行的写入数据
writer.writerow(['name', 'age', 'score'])

# 还可以调用writerows方法，一次性写入多行数据
writer.writerows([['zhangsan', '18', '98'],['lisi', '20', '99'], ['wangwu', '17', '90'], ['jerry', '19', '95']])
file.close()
```



### CSV文件的读取

```python
import csv

# 以读取方式打开一个csv文件
file = open('test.csv', 'r')

# 调用csv模块的reader方法，得到的结果是一个可迭代对象
reader = csv.reader(file)

# 对结果进行遍历，获取到结果里的每一行数据
for row in reader:
    print(row)

file.close()
```



