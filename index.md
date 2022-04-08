## 欢迎来到这个网页.jpg
不过我想稍作修改（
### 2022年1月4日

今天打算写一个日常签到的机器人插件，其功能有：

​	获取用户ID

​	获取执行时间（防止单位时间（每日）内签到多次）

​	随机获得签到所得“货币”（用来解锁后续功能）

​	随机获得好感值（用来解锁后续功能）

为了完成这个功能需要使用数据库来存储这些数据，毕竟不能获得这些数据不处理就结束。

我使用的是MySQL数据库。

​	首先导入pymysql模块

```python
import pymysql
```

​	创建数据库连接（建表过程略）

```python
# 连接数据库
db = pymysql.connect(host='地址', port=端口号, user='用户名', passwd='密码', db='要操作的数据库', charset='utf8')
# 创建游标
cursor = db.cursor()
```

​	然后导入日期处理模块datetime

```python
import datetime
```

​	使用了datetime.date.today()来获取当前日期

```python
dt1 = datetime.date.today()
```
到这里结束。

### 2022年1月18日

今天打算写一个，呃，商店功能，大概如下：

商店：
​		输出商品列表（以及所花费的金额）

​		选择购买的商品及其数量

​		在“结账”时，判断是否有足够的金额来支付“订单”

​		支付完成后，扣除花费的金额，获得购买的商品，存入“背包”（目前未实现）

```python
# 商店菜单
welcome = ["欢迎来到商店，这次想买些什么呢？"]
goods_dict = {"刨冰" : "2",
        "草饼":"4",
        "游戏卡带":"10",
        "游戏机":"50"}
for i,item in enumerate(goods_dict.items(),start=1):
    k,v =item
    # 调整商店菜单的输出（出于美观考虑，大概）
    welcome.append(f"{i}.{k.ljust(6,'　')}{v.rjust(4)}硬币")
```

```python
# 以下使用伪代码
if 输入的商品 in goods_dict.keys():
    输入的数量
    查询拥有的“钱”
    查询本次要花多少“钱”
    有钱就花，没钱就提示买不起
    if 有钱：
        扣除钱，获得商品
    else:
        print("买不起")
```



### 2022年3月4日

今天修改之前httpx异步get请求的问题：

```python
    async with httpx.AsyncClient() as client:
        query = await client.get(url)
        assert query.status_code == 200
        requery = query.text
        #上面的代码是直接复制粘贴的
```

在后面调用时出现了意料之外的错误：

```
TypeError: string indices must be integers
```

于是我使用了print(requery)来查看输出结果，发现和修改之前输出结果一致，即正常结果。

我看到这个query.text就想到是不是和处理的格式有关系，后修改为

```python
requery = query.json()
```

代码正常运行。

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
