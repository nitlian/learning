
1、 创建表名为student， 有两个列族info，score
create 'student','info','score'


2. put数据 忘student表中插入一条列族为info， 列名为name， 值为xiaoming 的数据， 切rowkey 为'00001'：
put 'student','00001','info:name','xiaoming'

put 'student','00001','info:age','23'

put 'student','00001','score:math','65'


put 'student','00002','info:name','xiaohong'

put 'student','00002','info:age','10'

put 'student','00002','score:math','100' 


3. 安全集群访问两个zk， 安全和非安全
spark.hadoop.hbase.client.zookeeper.config.path=./conf.txt
spark.yarn.dist.innerfiles={end},{path}/conf.txt
spark.yarn.security.credentials.hbase.enabled = true

 conf.txt: zookeeper.sasl.client=false

