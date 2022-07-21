# Work Sample for Data Aspect, PySpark Variant

[What is this for?](https://github.com/EQWorks/work-samples#what-is-this)

## Environment setup

If you already have a functioning Apache Spark configuration, you can use your own. For your convenience, the provided `docker-compose.yml` is based on the [`jupyter/pyspark-notebook`](https://github.com/jupyter/docker-stacks/tree/master/pyspark-notebook) image. You will need to have Docker and Docker Compose configured on your computer. Check out the [Docker Desktop documentation](https://docs.docker.com/desktop/) for details.

You can run `docker-compose up` and follow the prompt to open the Jupyter Notebook UI (looks like `http://127.0.0.1:8888/?token=<SOME_TOKEN>`).

The given `data/` directory mounts as a Docker volume at `~/data/` for easy access:

```python
import os
from pyspark.sql import SparkSession

spark = SparkSession.builder.master('local').getOrCreate()
df = spark.read.options(
    header='True',
    inferSchema='True',
    delimiter=',',
).csv(os.path.expanduser('~/data/DataSample.csv'))
```

![example](https://user-images.githubusercontent.com/2837532/110395132-9ff52100-803b-11eb-93c0-88b0a8e955e0.png)

## Submission

Please host your solution as one or multiple Notebooks (`.ipynb`) in a public git remote repository and reply with its link to the email thread you initially received to work on this work sample.
