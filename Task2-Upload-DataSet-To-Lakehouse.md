[Home](README.md) -  [Next Task (Warehouse Setup) >](Task4-Setting-up-the-Warehouse.md)

### Task 2: Upload File To Lakehouse

In this task we upload a file to LakehouseSpark. We will use this data to run some spark commands to get a basic understanding on spark functions.

-----------------------------------------------------------------------------------------


**Download** Orders.CSV file from [Here](Dataset)


1. **Open** [Power BI](https://app.powerbi.com/)

2. In PowerBI, **click** 'Workspaces' and **select** 'FabricSparkWS'

3. In 'FabricSparkWS' workspace, **click** on 'LakehouseSpark' lakehouse.

4. to upload a file,  **Click** on the three dots in front of Files --> Upload --> Upload files. Click on browse button and select the Orders.csv file that's been download in previous step.
   
6. **Click** on 'New shortcut'.

	![Lakehouse.](media/lakehouse-2.png)

7. In the pop-up window, under External sources **select** 'Azure Data Lake Storage Gen2'

	![Lakehouse.](media/demo-9.png)

8. In a new tab **open** the resource group created in [Task 2](#task-2-run-the-cloud-shell-to-provision-the-demo-resources) while script execution with name 'fabric-dpoc-...'.

9. **Search** for 'storage account', **click** the storage account resource.

	![Lakehouse.](media/demo-10.png)

10. In the resource window **goto** the left pane and **scroll down**.
11. In 'Security + networking' section, **click** 'Access keys'.
12. **Click** 'Show' button under key1.

	![Lakehouse.](media/demo-11.png)

13. **Click** 'Copy to clickboard' button.
14. **Save** it in a notepad for further use.

	![Lakehouse.](media/demo-12.png)

15. **Scroll down** in the left pane.
16. **Select** 'Endpoints' from 'Settings' section.
17. **Scroll down** and **copy** the 'Data Lake Storage' endpoint under 'Data Lake Storage' section.
18. **Save** it in a notepad for further use.

	![Lakehouse.](media/demo-12.1.png)

>**Note:** You may see different endpoints as well in the above screen. Make sure to select only the Data Lake Storage endpoint.

19. **Navigate back** to Power BI workspace i.e. the powerbi tab.
20. **Paste** the endpoint copied under the 'URL' field.

21. In the 'Authentiation kind' dropdown, **select** 'Account Key'.

22. **Paste** the account key copied.

23. **Click** on 'Next'.

	![Lakehouse.](media/demo-12.2.png)

24. Under Shortcut Name **type** 'sales-transaction-litware'.

25. **Verify** the URL is same as the one you copied in step 17.

26. Under Sub Path **type** '/bronzeshortcutdata'.

27. **Click** the **Create** button.

	![Lakehouse.](media/lakehouse-3.png)

Now you should see a shorcut created in lakehouseBronze with name 'sales-transaction-litware'. This will have files/folders that ADLS Gen2 bronzeshortcutdata container has.

 [Continue >](Task4-Setting-up-the-Warehouse.md)


