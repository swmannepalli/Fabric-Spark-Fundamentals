[Home](README.md) -  [Next Task (Warehouse Setup) >](Task4-Setting-up-the-Warehouse.md)

### Task 4:  Create Notebook and Run Code

In this task we create a notebook and run spark commands to analyse the data. 

-----------------------------------------------------------------------------------------

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'LakehouseSpark' lakehouse.

4. **Click** on Open notebook --> New notebook. Make sure LakehouseSpark is attached to the Notebook by checking the Lakehouses option under Explorer.

   <img width="833" alt="image" src="https://github.com/swmannepalli/Fabric-Spark-Fundamentals/assets/84516667/70792fea-1c85-40b6-aea3-cc3da7765b36">

**Magic Commands:**
Magic commands are special commands that provide additional functionalities in Microsoft Fabric Spark notebooks. In this task we will use few magic commands to show how the code cell behavior changes. 

Magic commands are easy to spot within the code as they have the prefix % or %% followed by the command name.

## 1. Load Data into Dataframe
   
In a Spark notebook, you could use the following PySpark code to load the file data into a dataframe and display the first 10 rows:

```
%%pyspark
df = spark.read.load('Files/Orders.csv',
    format='csv',
    header=True
)
display(df.limit(10))

```
Click on Run Cell.

>**Note:** It is going to take time to run the first cell as it is taking time to start the cluster.


**Equivalent Scala code for the Orders data example:**
   
>**Note:** Hover over the bottom of the output and click on +Code to add new cell

```
%%spark
val df = spark.read.format("csv").option("header", "true").load("Files/Orders.csv")
display(df.limit(10))

```
Click on Run Cell.   


 [Continue >](Task4-Setting-up-the-Warehouse.md)
