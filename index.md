## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/coderrbk/Blogger/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
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

​	
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/coderrbk/Blogger/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
