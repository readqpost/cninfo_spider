# 用处

爬取巨潮资讯网，将指定企业从2000年至今所有的年报pdf文件批量下载至指定的文件夹。

# 使用方式

- 将"年报信息获取.py"中 `stock_code` 变量赋值为想要查询的上市公司的股票代码
- 运行"年报信息获取.py"文件，将对应股票的所有年报信息下载入"pdf_to_download.csv"文件中
- 运行"年报下载.py"文件，借助"pdf_to_download.csv"文件中的信息下载对应年报

# 实现原理

- 向巨潮资讯网公告信息查询界面发送post请求，获取给定查询信息后返回的json文件，解析后即为公告pdf文件的基础信息和url关键信息。
- 借助解析后的公告文件信息，向巨潮资讯网中存放公告pdf的url发送请求，批量下载对应的公告，下载后的公告按照公司代码整理至对应的文件夹。

# 难点

- post请求查询公告信息时需要公司的orgId值，该值需要通过抓包找到股票代码和orgId的对应关系，手动建立映射。

# 待实现功能

- 单次运行时可以下载多家公司的年报
- 下载招股说明书等其他常用的公告数据