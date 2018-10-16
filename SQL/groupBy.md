## Group By 查询问题

```
Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'userinfo.
```

解决：

执行以下两个命令：
```
mysql> set global sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
mysql> set session sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
```
--------------------- 
作者：fansili 
来源：CSDN 
原文：https://blog.csdn.net/fansili/article/details/78664267?utm_source=copy 
版权声明：本文为博主原创文章，转载请附上博文链接！
