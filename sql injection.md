# 发货100-设计素材下载系统 1.1 Value parameter has SQL injection


## Vulnerability Type :
SQL Injection


## Vulnerability Version :
1.1


## Recurring environment:
* Windows 10
* PHP 7.3
* Apache 2.4.39


## Vulnerability Description AND recurrence:
Source code download link：http://down.chinaz.com/soft/42490.htm

When the admin user edits the commodity information, SQL injection is caused.

Reason: when getting user IP, there is no filtering.

/conn/function.php
![4.JPG](https://i.loli.net/2021/03/25/wf1mNr3Uo4PzSk7.jpg)

visit /admin/product_add.php?

Modify the product information and click save

![1.JPG](https://i.loli.net/2021/03/25/5612kEpRCGTjJo3.jpg)
![2.JPG](https://i.loli.net/2021/03/25/A4ODF8SCPyWjqat.jpg)

use burpsuite and modify X-Forwarded-For:'|| sleep(2) || '

![3.JPG](https://i.loli.net/2021/03/25/qL8Jl5UM2YjowfK.jpg)

Successful injection！
