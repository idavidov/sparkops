# sparkops


1. Standalone Spark documenttation
https://spark.apache.org/docs/latest/spark-standalone.html


2. why standalone
try to test ability without build unnessesary complicated env
also seems it will be easier to deploy on LSF/k8s/clouds
/**
 * @todo ETL
 * @body  from LSF, check ELK or xdmod, need prepare code for other DRM, univa, AWS
*/
3. Java
export JAVA_HOME=/Library/Java/JavaVirtualMachines/amazon-corretto-11.jdk/Contents/Home


4.start
cd /Users/idavidov/nWIP/spark/tmo/spark-3.0.0-bin-hadoop3.2 \n
./sbin/start-master.sh
./sbin/start-slave.sh spark://mac-idavidov:7077

available now @
http://localhost:8080


# Load trainsched.txt
df = spark.read.csv("trainsched.txt", header=True)

# Create temporary table called table1
df.createOrReplaceTempView("table1")

spark.sql("DESCRIBE table1").show()
