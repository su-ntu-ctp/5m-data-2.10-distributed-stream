# Assignment

## Brief

## Instructions

### Question 1

Question: Calculate the average no. of pizzas (count) by shop.

```python
from pyspark.sql.functions import from_json, col
from pyspark.sql.types import StringType, IntegerType, LongType, DoubleType, StructType, ArrayType, StructField

pizza_df = spark.read.format('kafka')\
    .options(**options)\
    .load()

pizza_schema = StructType([
  StructField("pizzaName", StringType()),
  StructField("additionalToppings", ArrayType(StringType())),
])

order_schema = StructType([
  StructField("address", StringType()),
  StructField("id", IntegerType()),
  StructField("name", StringType()),
  StructField("phoneNumber", StringType()),
  StructField("shop", StringType()),
  StructField("cost", DoubleType()),
  StructField("pizzas", ArrayType(pizza_schema)),
  StructField("timestamp", LongType()),
])

parsed_df = pizza_df.select("timestamp", from_json(col("value").cast("string"), order_schema).alias("value"))
```

Answer:

```python

```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
