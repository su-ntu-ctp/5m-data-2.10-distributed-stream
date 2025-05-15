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
docker run -d --name broker -p 9092:9092 apache/kafka:latest 
```

```
docker exec --workdir /opt/kafka/bin/ -it broker sh
```

```
./kafka-topics.sh --bootstrap-server localhost:9092 --create --topic pizza-orders
```

Full removal at the end: 

```
docker rm -f broker
```

Reference: https://hub.docker.com/r/apache/kafka


---

## Part 1 - Event Streaming and Stream Processing

Conceptual knowledge, refer to slides.

---

## Part 2 - Hands-on with Kafka

We will be using the notebooks
* notebook/5m_data_2_10_01_Fake_Data_Kafka_Producer.ipynb
* notebook/5m_data_2_10_02_Hands_on_with_Kafka.ipynb

for this section.

Alternatively, we can use [this](https://colab.research.google.com/drive/1WwwGa-tVIqr2aNLPrxqFqFyQAwrxU1JD?usp=sharing) Colab notebook for this section.

If you are using the Colab notebook:
> Open the Colab link, then go to File -> Save a copy in Drive. This will create a copy of the notebook in your Google Drive. It will then open the notebook in a new tab.
>
> Follow on with the lesson in the notebook.

## Part 3 - Hands-on with Spark (Structured Streaming)

We will be using the notebook
* notebook/5m_data_2_10_03_Hands_on_with_Spark_(Structured_Streaming).ipynb

for this section.

Alternatively, we can use [this](https://colab.research.google.com/drive/1xSEbQmCNqW0HdyD8Z4jwKqCffTb28W7q?usp=sharing) Colab notebook for this section.

If you are using the Colab notebook:
> Open the Colab link, then go to File -> Save a copy in Drive. This will create a copy of the notebook in your Google Drive. It will then open the notebook in a new tab.
>
> Follow on with the lesson in the notebook.
