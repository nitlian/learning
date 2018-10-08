1. 调试参数
在IDEA中添加
-Xdebug -Xnoagent -Xrunjdwp:transport=dt_socket,address=8764,server=y,suspend=y 
在Spark/spark/conf 配置项中添加
配置driver和Execute的extraJavaOptions

nohup ./spark-submit --master yarn-client --jars /opt/lian/GroupByTest_1.jar,http://10.186.61.150:8081/nexus/content/groups/V1R2C20-GROUP/aopalliance/aopalliance/1.0/aopalliance-1.0.jar  --class com.huawei.test.GroupByTest /opt/lian/GroupByTest.jar > report.log 2>&1

./spark-submit --master yarn-cluster  --class com.huawei.test.GroupByTest /srv/lian/GroupByTest.jar 


export SPARK_SUBMIT_OPTS="-Xdebug -Xnoagent -Xrunjdwp:transport=dt_socket,address=8764,server=y,suspend=y"


在Spark/conf/java-opts 最后添加"-Xdebug -Xnoagent -Xrunjdwp:transport=dt_socket,address=8764,server=y,suspend=y"


SPARK_SUBMIT_OPTS="-Dlog4j.configuration=file:/opt/client//Spark/spark/conf/log4j.properties -Djetty.version=x.y.z -Dzookeep
er.server.principal=zookeeper/hadoop.hadoop.com -Djava.security.krb5.conf=/opt/client/KrbClient/kerberos/var/krb5kdc/krb5.conf -Djava.sec
urity.auth.login.config=/opt/client//Spark/spark/conf/jaas.conf -Dorg.xerial.snappy.tempdir=/opt/client//Spark/tmp -Dcarbon.properties.fi
lepath=/opt/client//Spark/spark/conf/carbon.properties"
