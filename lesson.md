# Lesson

## Brief

### Preparation and Lesson Overview

Ensure you have conda setup. Please do:

```
conda env update -f environment.yml
```

This should install the `kafka` conda environment. You can activate it via:

```
conda activate kafka
```

Lastly, one more step to install the packages:

```
pip install -r requirements.txt
```

Also, we need to host kafka locally via docker: 

```
docker run -d --name broker apache/kafka:latest -p 9092:9092
```

```
docker exec --workdir /opt/kafka/bin/ -it broker sh
```

```
./kafka-topics.sh --bootstrap-server localhost:9092 --create --topic pizza-orders
```



---

## Part 1 - Event Streaming and Stream Processing

Conceptual knowledge, refer to slides.

---

## Part 2 - Hands-on with Kafka

We will be using [this](https://colab.research.google.com/drive/1WwwGa-tVIqr2aNLPrxqFqFyQAwrxU1JD?usp=sharing) Colab notebook for this section.

> Open the Colab link, then go to File -> Save a copy in Drive. This will create a copy of the notebook in your Google Drive. It will then open the notebook in a new tab.
>
> Follow on with the lesson in the notebook.

## Part 3 - Hands-on with Spark (Structured Streaming)

We will be using [this](https://colab.research.google.com/drive/1xSEbQmCNqW0HdyD8Z4jwKqCffTb28W7q?usp=sharing) Colab notebook for this section.

> Open the Colab link, then go to File -> Save a copy in Drive. This will create a copy of the notebook in your Google Drive. It will then open the notebook in a new tab.
>
> Follow on with the lesson in the notebook.
