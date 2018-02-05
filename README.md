march action

# Cassandra-API :



# spring-boot-cassandra:

create keyspace boot_keyspace with replication = {'class':'SimpleStrategy', 'replication_factor':1};
use boot_keyspace;
select * from  library ;

CREATE TABLE library (
       id bigint PRIMARY KEY,
       question text,
       createTime timestamp,
       updateTime timestamp
    );


use lee_keyspace;

select * from  products ;


apache-cassandra-3.11.1

# Table Data Type :
* http://docs.datastax.com/en/archived/cql/3.0/cql/cql_reference/create_table_r.html

* http://blog.csdn.net/codeforjesus/article/details/53337317


# Apache Cassandra

* wget http://archive.apache.org/dist/cassandra/3.0.9/apache-cassandra-3.0.9-bin.tar.gz

* wget http://archive.apache.org/dist/cassandra/3.11.1/apache-cassandra-3.11.1-bin.tar.gz


# Start Boot

* java  -jar  *.jar   --spring.profiles.active=dev

* https://docs.spring.io/spring-boot/docs/current/reference/html/common-application-properties.html

# debezium binlog subscribe :

* debezium


# Zookeeper Install :

* wget https://archive.apache.org/dist/zookeeper/zookeeper-3.4.6/zookeeper-3.4.6.tar.gz
* wget https://archive.apache.org/dist/zookeeper/zookeeper-3.4.5/zookeeper-3.4.5.tar.gz


# Check Cluster Status :

./nodetool status


# Cassandra Cluster Conf :
* cluster_name: 'monitorCluster'
* seed_provider:
* - class_name: org.apache.cassandra.locator.SimpleSeedProvider
* parameters:
* - seeds: "192.168.0.111,192.168.0.112"
* listen_address:192.168.0.111
* rpc_address: 192.168.0.111



# Update Cassandra Cluster Name :
修改集群名称步骤

更新集群名称字段

cqlsh> UPDATE system.local SET cluster_name = '新集群名称' where key='local';
1
修改Cassandra.yaml中的cluster_name为新集群名称

将memtable刷为commitlog

shell> nodetool flush system
1
验证集群名称

cqlsh> select cluster_name from system.local;




# Cassandra Cql3
INSERT INTO library (id,createtime,question,updatetime) VALUES (uuid(), dateof(now()),'PgXOp', dateof(now()));










