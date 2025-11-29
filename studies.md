# **Self-Study Preparation Guide**

**⏳ Estimated Prep Time:** 30–45 minutes

Welcome to our flipped-classroom session, where you'll review foundational concepts beforehand to maximize our time for hands-on coding and debugging. This pre-study focuses on Real-Time Data Streaming using **Apache Kafka** and **Spark Structured Streaming**. In the modern data landscape, the ability to process events as they happen—rather than waiting for end-of-day batches—is critical for industries ranging from logistics to finance.

## **⚡ Your Self-Study Tasks**

Please complete the following activities before our session.

### **📝 Task 1: Preparation (10 Minutes)**

**Activity:** Complete the steps described  **"Preparation and Lesson Overview"** section in `lesson.md` to prepare your environment before the session. 

**Guiding Questions:**

* We use Docker to host Kafka locally. Why is docker run used to pull the `apache/kafka:latest` image rather than installing Kafka directly on your OS?  
* What is the relationship between the Zookeeper/Broker container and the Python scripts we will run?

### **📝 Task 2: Understanding the Event Source (Kafka) (15 Minutes)**

**Activity:** Review the **"Hands-on with Kafka"** notebook (`5m\_data\_2\_10\_02\_Hands\_on\_with\_Kafka.ipynb`). Pay close attention to how we simulate a real-world scenario using a "Pizza Order" generator.

**Focus your attention on these key components:**

1. **The Producer:** How data is generated. We are simulating a pizza chain with shops like "Marios Pizza" and "Luigis Pizza".  
2. **Serialization:** Notice that we send data as JSON. In production, we might use binary formats like Avro, but for this session, we deserialize using `json.loads`.  
3. **Offsets:** We set `auto\_offset\_reset='earliest'` to ensure we read from the beginning of the history.

**Guiding Questions:**

* Why do we need to serialize data (turn it into bytes) before sending it to a Kafka cluster?  
* Look at the output of the consumer loop. What metadata accompanies the actual pizza order JSON (e.g., partition, offset)?

### **📝 Task 3: The "Unbounded Table" Concept (Spark) (20 Minutes)**

**Activity:** Open the **"Hands-on with Spark (Structured Streaming)"** notebook `(5m\_data\_2\_10\_03\_Hands\_on\_with\_Spark\_(Structured\_Streaming).ipynb)`. **You do not need to run the code yet.** Read the markdown introduction and review the diagrams provided.

**Focus your attention on these key components:**

1. **Stream as a Table:** Structured Streaming treats a live data stream as a table that is being continuously appended.  
2. **Micro-batching:** Spark processes these streams as a series of small batch jobs to achieve fault tolerance and low latency.  
3. **Schema Definition:** Unlike standard Python scripts, Spark Streaming requires a strict schema (`StructType`) to parse the JSON data effectively.

**Guiding Questions:**

* How does the "Input Table" concept differ from a static CSV file you might have worked with previously?  
* We define a `pizza\_schema and an order\_schema`. Why is a nested schema necessary for the pizzas field?  
* Review the code block handling `shop\_counts`. What does `.outputMode("complete")` imply about how the data is written to the console?


## **🙌🏻 Active Engagement Strategies**

To deepen your retention, try one of the following while you review:

* **"Code Commentary":** Select the complex schema definition block in the Spark notebook. Write a brief comment explaining *why* specific data types (like `ArrayType` or `LongType`) were chosen for the pizza toppings or timestamps.  
* **Scenario Matching:** We are using Pizza Orders as our data. Imagine a generic e-commerce site. What fields would replace "Toppings" and "Pizza Name" in that scenario?  
* **Visual Tracing:** Sketch the flow of data: *Fake Data Generator* \-\> *Kafka Topic (pizza-orders)* \-\> *Spark Structured Stream* \-\> *Aggregation (Count)* \-\> *Console Output*.

## **📖 Additional Reading Material**

* [Structured Streaming Programming Guide (Apache Spark)](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html) \- *Referenced conceptually in the notebook regarding the "Stream as a Table" model.*  
* [Event Streaming](https://tanzu.vmware.com/event-streaming)

### **🙋🏻‍♂️ See you in the session\!**

