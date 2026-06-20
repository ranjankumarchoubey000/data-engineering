# data-engineering

# Install SDKMAN
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"


sdk install java 11.0.21-tem
sdk install scala 2.13.14
sdk install sbt 1.9.7


# Download Spark 3.5.8 pre-built for Hadoop 3
wget https://dlcdn.apache.org/spark/spark-3.5.8/spark-3.5.8-bin-hadoop3.tgz

# Extract (this is ~400 MB, takes a minute)
tar -xzf spark-3.5.8-bin-hadoop3.tgz

# Move to standard location
sudo mv spark-3.5.8-bin-hadoop3 /opt/spark

# Set environment variables
echo 'export SPARK_HOME=/opt/spark' >> ~/.bashrc
echo 'export PATH=$PATH:$SPARK_HOME/bin' >> ~/.bashrc
source ~/.bashrc

# Verify
spark-shell --version
# version 3.5.8
# Using Scala version 2.12.18  ← NOTICE: confirms Scala 2.12

# What's in the Spark bin directory?
ls $SPARK_HOME/bin/
# spark-shell       ← Scala REPL with SparkSession
# pyspark           ← Python REPL with SparkSession
# spark-submit      ← submit jobs to cluster
# spark-sql         ← SQL-only shell
# spark-class       ← internal launcher


# ===== VERIFICATION CHECKLIST =====
# 1. Java
java -version
#   openjdk version "11.0.x"

javac -version
#   javac 11.0.x

echo $JAVA_HOME
#   /usr/lib/jvm/java-11-openjdk-amd64

# 2. Scala
scala -version
#   Scala code runner version 2.12.18

# 3. sbt
sbt --version
#   sbt script version: 1.9.x

# 4. Spark
spark-shell --version
#   version 3.5.8, Using Scala version 2.12.18
