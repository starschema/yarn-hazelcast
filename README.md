YARN-Hazelcast integration
==========================

This is the modification of the Apache YARN Distributed Shell's source to simplify the process of Hazelcast cluster setup and to take advantage of the amazing YARN resource negotiation capabilities. All it requires is the Hazelcast zip file (after the necessary configuration modifications). It starts Hazelcast instances on the provided number of cluster nodes. The nodes discover each other (tested with discovery by TCP) and successfully form a cluster. No setup of Hazelcast on the nodes is required, only a functional Hadoop cluster is needed. 

Usage
=====

Distributed Shell's original arguments have been appended with the hazelcast_zip option to provide the location of the Hazelcast zip file. For example: 

hadoop jar yarn-hazelcast.jar org.starschema.hadoop.yarn.applications.distributedshell.Client --jar yarn-hazelcast.jar --shell_command start.sh --hazelcast_zip hazelcast-3.4.6.zip 

Replace the shell_command argument with a file containing commands like:
 
cd Hazelcast.zip/hazelcast-3.4.6/bin
./server.sh

DO NOT change the first part (Hazelcast.zip), but change the rest according to start.sh's location inside your Hazelcast zip archive.


