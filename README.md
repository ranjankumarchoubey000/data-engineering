# Scala : Episode 1, Part-2

## Install SDKMAN

```bash
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

## Install Java, Scala and sbt

```bash
sdk install java 11.0.21-tem
sdk install scala 2.13.14
sdk install sbt 1.9.7
```

## Download Apache Spark 3.5.8 (Pre-built for Hadoop 3)

```bash
wget https://dlcdn.apache.org/spark/spark-3.5.8/spark-3.5.8-bin-hadoop3.tgz
```

## Extract Spark

```bash
tar -xzf spark-3.5.8-bin-hadoop3.tgz
```

## Move Spark to a Standard Location

```bash
sudo mv spark-3.5.8-bin-hadoop3 /opt/spark
```

## Configure Environment Variables

```bash
echo 'export SPARK_HOME=/opt/spark' >> ~/.bashrc
echo 'export PATH=$PATH:$SPARK_HOME/bin' >> ~/.bashrc
source ~/.bashrc
```

## Verify Spark Installation

```bash
spark-shell --version
```

Expected output:

```text
version 3.5.8
Using Scala version 2.12.18
```

## Explore Spark Commands

```bash
ls $SPARK_HOME/bin/
```

Common tools:

* `spark-shell` — Scala REPL with SparkSession
* `pyspark` — Python REPL with SparkSession
* `spark-submit` — Submit jobs to a Spark cluster
* `spark-sql` — Interactive SQL shell
* `spark-class` — Internal Spark launcher

---

# Verification Checklist

## 1. Java

```bash
java -version
javac -version
echo $JAVA_HOME
```

Expected:

```text
openjdk version "11.0.x"
javac 11.0.x
/usr/lib/jvm/java-11-openjdk-amd64
```

## 2. Scala

```bash
scala -version
```

Expected:

```text
Scala code runner version 2.12.18
```

## 3. sbt

```bash
sbt --version
```

Expected:

```text
sbt script version: 1.9.x
```

## 4. Spark

```bash
spark-shell --version
```

Expected:

```text
version 3.5.8
Using Scala version 2.12.18
```
