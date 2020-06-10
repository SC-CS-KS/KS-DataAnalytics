# 数据分析架构

## DW/BI整体架构

完整的数据平台
	操作型源系统（数据来源）
	ETL系统（抽取、转换、加载）；
	支持BI的展现区（DW，以维度维度模型构建的OLAP数据库）
	BI应用（报表等）

## 基础架构分类

使用Hadoop/Spark 的MR 分析  
将Hadoop/Spark 的结果注入RDBMS 中提供实时分析  
将结果注入到容量更大的NoSQL 中，例如HBase 等  
将数据源进行流式处理，对接流式计算框架，如Storm，结果落在RDBMS/NoSQL 中。
将数据源进行流式处理，对接分析数据库，例如Druid、Vertica 等。

## 技术栈 Pipeline

* 两种常用方式    

Data Source -> HDFS -> MR/Hive/Spark(相当于ETL) -> 
	HDFS Parquet -> SparkSQL/impala -> Result Service
Data Source -> Real time update data to HBase/DB ->
	 Export to Parquet -> SparkSQL/impala -> Result Service
	也可以通过Kafka+Spark Streaming+Spark SQL

* 期待的方式  

Data Source -> Kafka -> Spark Streaming -> Parquet -> 
	Spark SQL（ML、Graphx等）-> Parquet -> 其他各种Data Mining等
