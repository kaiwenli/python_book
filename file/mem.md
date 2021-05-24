## 内存中写入数据

除了将数据写入到一个文件以外，我们还可以使用代码，将数据暂时写入到内存里，可以理解为数据缓冲区。Python中提供了StringIO和BytesIO这两个类将字符串数据和二进制数据写入到内存里。

### StringIO

StringIO可以将字符串写入到内存中，像操作文件一下操作字符串。

```python
from io import StringIO

# 创建一个StringIO对象
f = StringIO()
# 可以像操作文件一下，将字符串写入到内存中
f.write('hello\r\n')
f.write('good')

# 使用文件的 readline和readlines方法，无法读取到数据
# print(f.readline())
# print(f.readlines())

# 需要调用getvalue()方法才能获取到写入到内存中的数据
print(f.getvalue())

f.close()
```

### BytesIO

如果想要以二进制的形式写入数据，可以使用BytesIO类，它的用法和StringIO相似，只不过在调用write方法写入时，需要传入二进制数据。

```python
from io import BytesIO

f = BytesIO()
f.write('你好\r\n'.encode('utf-8'))
f.write('中国'.encode('utf-8'))

print(f.getvalue())
f.close()
```



