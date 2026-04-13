# CDP-CM-From-Scratch

What is CM (Cloudera Manager)?
> Cloudera Manager is a management tool used to install, configure, and monitor Hadoop ecosystem services in a cluster.
It provides a web UI to easily manage services like HDFS, YARN, Hive, and Spark.
> CM server is designed in JAVA ,CM agents are designed in python.
> Targetd version 7.11.3.14
> CM server and CM agent are two main components that work together to access and monitor service health.



What is CDP (Cloudera Data Platform)?
> Cloudera Data Platform (CDP) is a modern data platform that provides tools for data engineering, data warehousing, machine learning, and analytics in a unified environment.
> Targeted verison 7.1.9.1000 


Basic Installation Steps:

1. Prerequisites
4 node cluster Linux machine (Bare metal CentOS/Ubuntu preferred) I am using CentOs 8.2 
Java installed (JDK 8 or 11 depending on version)
Static IP configuration
SSH access between nodes
Sufficient RAM and CPU for cluster setup
Python 3.11 verison 
Selinux disabled and Firewalld disabled for simplicity of configuration

Primary source of trusth for understading CDP and CM compatibilty kinldy refer https://supportmatrix.cloudera.com/

You can choose any version of CM and CDP for understanding the tech stack I am going for LTS version (trial licenses)

CM download:
<pre>
https://username:password@archive.cloudera.com/p/cm7/patch/7.11.3.14/redhat8/yum
https://username:passwor@archive.cloudera.com/p/cm7/patch/7.11.3.14/redhat8/yum/cloudera-manager.repo
</pre>

CDP runtome download : 
<pre> https://username:passwor@archive.cloudera.com/p/cdh7/7.1.9.1000/parcels </pre>


You can try the Cloudera Private Cloud Base Edition of Cloudera Data Platform for 60 days without obtaining a license key file.



sudo rpm --import https://username:password@archive.cloudera.com/p/cm7/7.11.3.14/redhat9/yum/RPM-GPG-KEY-cloudera

<pre> /etc/yum.repos.d/cloudera-manager.repo
[cloudera-manager]
name=Cloudera Manager 7.11.3
baseurl=https://username:password@archive.cloudera.com/p/cm7/patch/7.11.3.14/redhat8/yum
gpgkey=https://username:password@archive.cloudera.com/p/cm7/patch/7.11.3.14/redhat8/yum/cloudera-manager.repo
gpgcheck=1
enabled=1
autorefresh=0
type=rpm-md
[postgresql10]
name=Postgresql 10
baseurl=https://archive.cloudera.com/postgresql10/redhat9/
gpgkey=https://archive.cloudera.com/postgresql10/redhat9/RPM-GPG-KEY-PGDG-10
enabled=1
gpgcheck=1
module_hotfixes=true </pre>

    

Cloudera manager related configurations:
/etc/default/cloudera-scm-server

Cloudera manager agent related configuration:
/etc/config.ini 
