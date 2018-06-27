# 简介
用于解析 Power Designer 16+ 生成的 .pdm 文件。

# 软件环境
JDK1.7+
 
# 如何使用
使用jar目录下的jar包 pdm-reader.jar或者自己编译生成，执行 `java -jar pdm-reader.jar [window或linux的pdm文件路径]` ，如下：

```
java -jar pdm-reader.jar /home/cjz/Desktop/tmp-doc/ZAFK.pdm
```
显示结果如下（终端上使用不同颜色区分，√为主键，M表示不为空）：

```
File  path:/home/cjz/Desktop/tmp-doc/ZAFK.pdm
Table size:122
 

------>NO.1 系统用户表 sys_users<-------
id                  VARCHAR(40)    40     √  M  用户ID
dept_id             VARCHAR(40)    40           所属机构
login_name          VARCHAR(50)    50           登录名
code                VARCHAR(20)    20           编码
name                VARCHAR(50)    50           姓名
name_cpa_first      VARCHAR(50)    50           姓名简拼
name_cpa_full       VARCHAR(512)   512          姓名全拼
sex                 VARCHAR(40)    40           性别   (来源字典表)
position            VARCHAR(40)    40           职务   (来源于字典表)
private_phone       VARCHAR(20)    20           联系电话
public_phone        VARCHAR(20)    20           办公电话
state               VARCHAR(1)     1            状态
order_number        INT4           4            顺序
remark              VARCHAR(255)   255          备注
created_at          timestamp                M  创建时间
updated_at          timestamp                M  更新时间

------>NO.2 组织机构表 sys_department<-------
id                  VARCHAR(40)    40     √  M  机构ID
code                VARCHAR(20)    20           机构编码
name                VARCHAR(50)    50           机构名称
name_cpa_first      VARCHAR(50)    50           名称简拼
name_cpa_full       VARCHAR(512)   512          名称全拼
parent_id           VARCHAR(40)    40           父ID
dept_level          VARCHAR(40)    40           级别   (数据来源于字典表中的组织机构级别)
division_code       VARCHAR(20)    20           行政区划代码
contacts            VARCHAR(20)    20           联系人
phone               VARCHAR(30)    30           联系电话
address             VARCHAR(100)   100          地址
order_number        INT4           4            序号
remark              VARCHAR(255)   255          备注
deleted_at          Timestamp                   删除时间
user_id             VARCHAR(40)    40           创建者id
created_at          Timestamp                   创建时间
updated_at          timestamp                M  更新时间
state               VARCHAR(1)     1            状态   (0--可用，1--禁用，2--逻辑删除)
longitude           DECIMAL(10,6)  10           经度
latitude            DECIMAL(10,6)  10           纬度


Use time:0.142s

说明： 表标题分别为 列代码/类型/长度/是否为主键/是否允许为空/列可读名称(及备注)
      √ 表示主键， M 表示不能为空
```
