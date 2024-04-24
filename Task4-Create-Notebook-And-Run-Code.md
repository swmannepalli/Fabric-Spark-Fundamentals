[Home](README.md) -  [Next Task (Work With Tables And SQL) >](Task5-Work-With-Tables-And-SQL.md)

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
df = spark.read.load('Files/products.csv',
    format='csv',
    header=True
)
display(df.limit(10))

```
Click on Run Cell.

>**Note:** It is going to take time to run the first cell as it is taking time to start the cluster.


**Equivalent Scala code for the products data example:**
   
>**Note:** Hover over the bottom of the output and click on +Code to add new cell

```
%%spark
val df = spark.read.format("csv").option("header", "true").load("Files/products.csv")
display(df.limit(10))

```
Click on Run Cell.   

## 2. Filtering and grouping Dataframe

You can use the methods of the Dataframe class to filter, sort, group, and otherwise manipulate the data it contains. For example, the following code example uses the select method to retrieve the Order ID and Sales columns from the df dataframe containing Order data in the previous example:

```
pricelist_df = df.select("ProductID", "ListPrice")

```
Click on Run Cell.

You can "chain" methods together to perform a series of manipulations that results in a transformed dataframe. For example, this example code chains the select and where methods to create a new dataframe containing the ProductName and ListPrice columns for products with a category of Mountain Bikes or Road Bikes:

```
bikes_df = df.select("ProductName", "Category", "ListPrice").where((df["Category"]=="Mountain Bikes") | (df["Category"]=="Road Bikes"))
display(bikes_df)

```
Click on Run Cell.

To group and aggregate data, you can use the groupBy method and aggregate functions. For example, the following PySpark code counts the number of products for each category:

```
counts_df = df.select("ProductID", "Category").groupBy("Category").count()
display(counts_df)

```

## 3. Saving a dataframe

You'll often want to use Spark to transform raw data and save the results for further analysis or downstream processing. The following code example saves the dataFrame into a parquet file in the data lake, replacing any existing file of the same name.

```
bikes_df.write.mode("overwrite").parquet('Files/product_data/bikes.parquet')

```
 [Continue >](Task5-Work-With-Tables-And-SQL.md)
