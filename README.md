factor_reader
================

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

# 相关链接

- [说明文档](https://chen-001.github.io/factor_reader/)
- [pypi](https://pypi.org/project/factor-reader/)
- [Github](https://github.com/chen-001/factor_reader)

## 安装与升级

- 首次安装

``` sh
pip install factor_reader
```

- 升级

``` sh
pip install factor_reader --upgrade
```

## 使用

factor_reader目前共包含两个功能：  
1. 查看目前包含哪些因子，以及每个因子的基本信息  
2. 读取某一因子在某段时间上的因子数据

``` python
import factor_reader

# 第一步：实例化一个FactorReader对象，输入token
token='xxxxxxxxxx'
fr=factor_reader.FactorReader(token)  

# 第二步：查看当前因子数据库中有哪些因子（此步骤可选）
fr.show_all_factors_information() # 展示所有可读取因子的相关信息

# 第三步：读取因子数据
## ①读取单日单个因子的数据
fr.read_factor('球队硬币',trade_date=20230113) # 读取球队硬币因子在2023年1月13日的因子数据
fr.read_factor('factor4',trade_date=20230113) # 读取方正金工多因子系列第4篇的因子在2023年1月13日的因子数据

## ②读取多个交易日单个因子的数据
fr.read_factor('球队硬币',start_date=20230101,end_date=20230113) # 读取球队硬币因子从2023年1月1日至2023年1月13日的因子数据
fr.read_factor('factor4',start_date=20230101,end_date=20230113,sql_like=True) # 以sql的形式，读取方正金工多因子系列第4篇的因子从2023年1月1日至2023年1月13日的因子数据

## ③读取多个交易日多个因子的因子数据
fr.read_factor(['球队硬币','云开雾散'],start_date=20230101,end_date=20230113) # 分别读取球队硬币因子和云开雾散因子从2023年1月1日至2023年1月13日的因子数据
fr.read_factor(['球队硬币','云开雾散','飞蛾扑火'],start_date=20230101,end_date=20230113,sql_like=True) # 以sql的形式，分别读取球队硬币因子、云开雾散因子、飞蛾扑火因子从2023年1月1日至2023年1月13日的因子数据
fr.read_factor(['球队硬币','云开雾散','飞蛾扑火'],trade_date=20230113,sql_like=True) # 以sql的形式，分别读取球队硬币因子、云开雾散因子、飞蛾扑火因子2023年1月13日的因子数据
```
