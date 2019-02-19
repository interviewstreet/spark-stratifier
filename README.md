# spark-stratifier
[![PyPI version](https://img.shields.io/pypi/v/spark-stratifier.svg)](https://img.shields.io/pypi/v/spark-stratifier)
[![Start with Why](https://img.shields.io/badge/start%20with-why%3F-brightgreen.svg?style=flat)](http://www.ted.com/talks/simon_sinek_how_great_leaders_inspire_action)

When we first started working Spark at HackerRank, we realized that within our dataset, the size of our outcome sets varied in size by quite a bit. This led to inconsistent model cross validation and training. However, with [**stratified sampling**](https://en.wikipedia.org/wiki/Stratified_sampling), we were able to eliminate these inconsistencies and improve overall model predictions. The goal of `spark-stratifier` is to provide a tool to stratify datasets for cross validation in `PySpark`. This class extends the current `CrossValidator` class in Spark.

Currently, the stratified cross validator works with binary classification problems using labels `0` and `1`.

Read more at [engineering.hackerrank.com](https://engineering.hackerrank.com/)

Requirements
------------
This tool is 100% Python and the only primary requirements are [`numpy`](https://github.com/numpy/numpy) and [`pyspark`](https://github.com/apache/spark/tree/master/python/pyspark).

Installation
------------
```
$ pip install spark-stratifier
```

Example
-------
You basically use this the exact same way you would with the Spark `CrossValidator`... except this time, your data will be stratified.

```py
from spark_stratifier import StratifiedCrossValidator

scv = StratifiedCrossValidator(
        estimator=pipeline,
        estimatorParamMaps=paramGrid,
        evaluator=evaluator,
        numFolds=8
      )

model = scv.fit(matrix)
```

Contributing
------------
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/interviewstreet/spark-stratifier/issues)

If you want to write some code and contribute to this project, go ahead and start a pull request. We hope this tool is useful for the community and we'd love to hear about how this helps solve your problems!
