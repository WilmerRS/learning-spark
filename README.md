<h1 style="margin-top:10px;" align="center"> 🐘
  <strong> Leaning Spark </strong> 📊
</h1>

## 🐧 Project explanation

Spark Learning Practices Repository for Big Data. 🌟

## ✅ Build

1. Run `build.sh` to create docker images in local.
2. Run `docker-compose up --remove-orphans` to serve.
3. Enjoy. 😄

## 🚀 Servers running

* JupyterLab at `http://localhost:8888`.
* Spark master at `http://localhost:8080`.
* Spark worker I at `http://localhost:8081`.
* Spark worker II at `http://localhost:8082`.

## ✏️ Usage example

```python
from pyspark.sql import SparkSession
import wget

spark = SparkSession.\
        builder.\
        appName("pyspark-notebook").\
        master("spark://spark-master:7077").\
        config("spark.executor.memory", "512m").\
        getOrCreate()


url = "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data"
wget.download(url)

data = spark.read.csv("iris.data")

data.show(n=5)
```
