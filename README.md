📝 *Start to write here and replace this text with your report*

---

## 🎯 Lab 1: Hadoop and Spark - Big Data Environment Setup

### 📚 Objective
This lab aims to establish a Big Data environment using Hadoop and Spark, fundamental tools in the Big Data ecosystem. Students will learn to set up these tools, configure them, and execute basic operations to ensure a functional environment for future data processing tasks.

### 📝 Tasks

#### 📌 Task 1: Joining the Classroom
- Join the classroom using the invitation link provided by your instructor after creating your GitHub account.
- Follow the instructions to join the classroom, granting access to course materials and assignment submissions.

#### 📌 Task 2: Joining the Course
- Once in the classroom, join the specific course related to this lab.
- Navigate to the course page within the classroom interface and follow the instructions to join.
- This step provides access to the course syllabus, schedule, and assignments.

#### 📌 Task 3: Setting Up the Environment
- Install and configure Hadoop and Spark on your local machine or use GitHub Codespaces for development.
- Ensure your machine meets the necessary system requirements for Hadoop and Spark.
- If using GitHub Codespaces:
  - Launch a virtual development environment in your browser by opening the repository and selecting "Open with Codespaces."
- For local setup:
  - Download Hadoop and Spark from their official pages.
  - Follow the installation instructions provided by the documentation.
- Verify correct installation by running basic commands:
  - `hadoop version`: Checks the installed version of Hadoop.
  - `spark-shell`: Launches the Spark shell for Scala.
  - `pyspark`: Launches the Spark shell for Python.
  - `spark-shell --master local[2]`: Launches Spark shell with two local worker threads.

#### 📌 Task 4: Software Installation and Configuration
- **Downloading Required Software:**
  - Download the appropriate versions of Hadoop and Spark compatible with your system and course requirements.
  - Obtain Hadoop from the [Apache Hadoop official page](https://hadoop.apache.org/releases.html) and Spark from the [Apache Spark official page](https://spark.apache.org/downloads.html).
- **Configuring the Software:**
  - After downloading, extract the software files.
  - Configure Hadoop and Spark to work in your environment:
    - Edit XML configuration files located in the `etc/hadoop` and `conf` directories for Hadoop and Spark, respectively.
    - Adjust configurations based on your specific setup and course requirements.
- **Verifying Installation:**
  - Confirm correct installation by running basic commands:
    - `hadoop version`: Checks the installed version of Hadoop.
    - `hadoop fs -ls /`: Lists the contents of the root directory in Hadoop's distributed file system.

#### 📌 Task 5: Running Simple Spark Programs
- Write and execute Spark programs to validate setup and execution in your environment. Explore various use cases for Spark programs, such as:
  - **Data Transformation:** Perform data transformations like filtering, mapping, and aggregating on large datasets.
  - **Machine Learning:** Implement machine learning algorithms for tasks like classification, regression, and clustering.
  - **Graph Processing:** Analyze graph data structures for applications such as social network analysis and recommendation systems.
  - **Real-time Streaming:** Process real-time data streams from sources like sensors, logs, or social media feeds.
  - **Text Analysis:** Conduct text mining and natural language processing tasks like sentiment analysis, topic modeling, and entity recognition.
  - **Geospatial Analysis:** Analyze spatial data for applications in GIS, location-based services, and urban planning.
  - **Image Processing:** Apply image processing techniques for tasks like object detection, image classification, and image segmentation.
  - **Time Series Analysis:** Analyze time series data for forecasting, anomaly detection, and trend analysis.
  - **Joining Datasets:** Perform join operations on multiple datasets to combine and analyze related information.

Two examples are provided below:

  - **Simple Data Analysis Program (Python):**
    ```python
    from pyspark.sql import SparkSession
    
    # Create SparkSession
    spark = SparkSession.builder.appName("SimpleDataAnalysis").getOrCreate()
    
    # Create DataFrame
    data = [("John", 25), ("Alice", 30), ("Bob", 35)]
    df = spark.createDataFrame(data, ["Name", "Age"])
    
    # Perform transformations and actions
    df.show()
    df.filter(df["Age"] > 30).show()
    ```

  - **Simple Data Analysis Program (Scala):**
    ```scala
    import org.apache.spark.sql.SparkSession
    
    // Create SparkSession
    val spark = SparkSession.builder().appName("SimpleDataAnalysis").getOrCreate()
    
    // Create DataFrame
    import spark.implicits._
    val data = Seq(("John", 25), ("Alice", 30), ("Bob", 35))
    val df = data.toDF("Name", "Age")
    
    // Perform transformations and actions
    df.show()
    df.filter($"Age" > 30).show()
    ```

  - **Pi Estimation Program (Python):**
    ```python
    from pyspark.sql import SparkSession
    import random
    
    # Create SparkSession
    spark = SparkSession.builder.appName("PiEstimation").getOrCreate()
    
    # Number of points to generate
    num_points = 1000000
    
    # Generate random points and count those inside the unit circle
    inside_circle = spark.sparkContext.parallelize(range(0, num_points)) \
                    .filter(lambda _: random.random()**2 + random.random()**2 < 1).count()
    
    # Estimate Pi
    pi_estimate = 4 * inside_circle / num_points
    print("Estimated Pi:", pi_estimate)
    ```

  - **Pi Estimation Program (Scala):**
    ```scala
    import org.apache.spark.sql.SparkSession
    
    // Create SparkSession
    val spark = SparkSession.builder().appName("PiEstimation").getOrCreate()
    
    // Number of points to generate
    val num_points = 1000000
    
    // Generate random points and count those inside the unit circle
    val inside_circle = spark.sparkContext.parallelize(0 until num_points)
                        .filter { _ =>
                          val x = math.random()
                          val y = math.random()
                          x * x + y * y < 1
                        }.count()
    
    // Estimate Pi
    val pi_estimate = 4.0 * inside_circle / num_points
    println(s"Estimated Pi: $pi_estimate")
    ```

- Submit your programs as `.py` or `.scala` files, depending on the language used.

---

## 🧠 Self-Check Questionnaire

### 🔍 Question 1:
Explain the purpose of Hadoop in the Big Data ecosystem and its relationship with distributed storage systems like HDFS.

### 🔍 Question 2:
Describe the key components of the Hadoop ecosystem and their respective roles in data processing and analysis.

### 🔍 Question 3:
Discuss the steps involved in setting up a Hadoop and Spark environment, highlighting important configuration parameters and potential challenges.

### 🔍 Question 4:
Identify common troubleshooting techniques for resolving issues during Hadoop and Spark installation and configuration.

### 🔍 Question 5:
Explain the significance of data locality in Hadoop and Spark processing and how it contributes to performance optimization.
