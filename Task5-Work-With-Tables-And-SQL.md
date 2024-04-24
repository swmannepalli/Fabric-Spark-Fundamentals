[Home](README.md) -  [Next Task (Visualize Data In A Spark Notebook) >](Task6-Visualize-Data-In-A-Spark-Notebook.md)

### Task 5: Work With Tables And SQL

In this task we use Spark SQL library to save the dataframe of products data as a table named products:

-----------------------------------------------------------------------------------------

1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'LakehouseSpark' lakehouse.

4. **Click** on Open notebook --> Existing notebook and open the notebook that is created in Task 4. Make sure LakehouseSpark is attached to the Notebook by checking the Lakehouses option under Explorer.

5. Add new code cell and paste below code to save the products.csv file as Table.

   ~~~
   df = spark.read.format("csv").option("header", "true").load("Files/products.csv")
   df.write.format("delta").saveAsTable("products")
   ~~~
6. Run the cell and go to the Lakehouse, expand Tables section and you should now see products table.

 [Continue >](Task6-Visualize-Data-In-A-Spark-Notebook.md)
