### python标准的文件头

```
    # coding=utf-8

```

* * *

###python中格式，进制，时间的转换

#### 格式转换

```
 int与char类型互转
 使用 chr() 函数将一个int类型转换为对应的char
 使用ord()函数将一个对应的char转换为int
     chr(ord('C')) = 'C'
    # 时间格式转换

```

#### 时间转换

```
import time,datetime
# 获取输入的时间
timeStr = "2015-03-12 23:40:32"
# 转换为时间戳
# 时间戳格式化
# %Y = 年
# %m 月
# %d 日
# %H  小时
# %M  分钟
# %S 秒
datetimeme = datetime.datetime.strptime(timeStr,'%Y-%m-%d %H:%M:%S')
# 获取datetime的时间戳
timeStapFromStr =  str(int(time.mktime(datetimeme.timetuple())))
# 根据时间戳，格式化输出当前的时间
time_cover = datetime.datetime.fromtimestamp(timestamp=int(timeStapFromStr))
print time_cover.strftime('%Y/%m/%d-%H:%M:%S')
# 打印出当前的时间
print datetime.datetime.fromtimestamp(int(time.time()))

# 计算时间差
# 计算 2014-06-23 到 现在的时间差
starttime = datetime.datetime.strptime('2014-06-23','%Y-%m-%d')
endtime  =  datetime.datetime.fromtimestamp(int(time.time()))

timedelta = endtime - starttime

print timedelta # 格式化了的时间
print str(int(timedelta.total_seconds())) # 相差的秒数

```

#### 进制转换

```
intDemo  = 660
# 转换为二进制
print bin(intDemo)
# 转换为16进制
print hex(intDemo)
#八进制
print oct(intDemo)

# 二进制转int
binDemo = '0b1010010100'

print int(binDemo,2)

```

* * *

### python中编码的转换(编码解码)

```
#coding:utf-8
a = '中文'
print type(a)
ustrDemo= u'中文'
print type(ustrDemo)# 此时a的类型为unicode
print ustrDemo
print type(ustrDemo.encode("utf-8")) # 此时a的类型为str
print ustrDemo

print len(a) # 6个字节
print len(ustrDemo)  #返回的是字符数量

print a,type(a)
print ustrDemo,type(ustrDemo)

# assert a == ustrDemo.decode()
print a == ustrDemo.encode('utf-8') # 原来ustrdemo是utf8编码过得数据，解码之后就成为了python中锋str类型

print a.decode("utf-8") == ustrDemo # 同理，使用decode可以获得str的编码

```

* * *

To Be continue
