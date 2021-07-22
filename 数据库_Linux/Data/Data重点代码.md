# Data重点代码


[TOC]

##### 1.1 拷贝文件

```python
"""
重点代码 !!

编写一个 函数 传入一个 图片,将该图片复制到
程序所在的文件夹下面，以当前日期命名保存

思路 ：　从源文件搞出内容，写入到新文件里边
　　　　* 如果文件比较大，循环的读写比较好？
       * 循环读写时候什么时候结束？
"""
import time

def copy(filename):
    """
    :param filename: 要拷贝的文件
    """
    fr = open(filename,'rb') # 源文件
    # 写文件
    file = "%s-%s-%s.jpg"%time.localtime()[:3]
    fw = open(file,'wb')
    # 一边读 一边写
    while True:
        data = fr.read(1024)
        if not data:
            break
        fw.write(data)
    fr.close()
    fw.close()

copy("./timg.jpg")
```

