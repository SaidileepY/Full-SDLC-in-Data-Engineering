# Full-SDLC-in-Data-Engineering
In this Data Engineering project I have Designed a End to End pipeline and a full SDLC of a Data Engineer's work.

![data architecture](https://github.com/user-attachments/assets/87823498-9957-4c49-925e-3c45498abb65)

You can connect with me on https://www.linkedin.com/in/sai-yamani-387325149/ 

In this SDLC for Data Engineering, I have data from multiple sources like CRM, APIs, SQL DB etc.,
As the project is about data from a Insurance company which is entered into CRM which gets automatically saved into SQL Server which is a onprem DB.
I have used Azure Data Factory for Orchestration where I used a basic Copy Activity to get the data from Source to ADLS Gen2 which I have used as my storage account.
I have created 3 containers named Bronze, Silver, Gold as I am using a medallion architecture.
I have used Incremetal Data Load and Schema Drift so that the pipeline can save time and work even if there is any change in the columns.
I used Event-Based trigger instead of Scheduled.
Monitor the performace of the pipeline using Azure monitor and send alerts to MS teams/Message/Email depends on the criticallity of the project.
Once the data is in Bronze layer Container, I use Mount to attach ADLS GEN2 to DataBricks, While Mounting I have used Azure KeyVault to store secret information and App Registration.
Once the data can be accessed in DataBricks, with the help of Pyspark, Spark SQL code I have performed data cleaning/data processing and store the data back to ADLS Gen2 in Delta format.
I have used Delta Format as it has Time Travel feature and ACID properties.
Once again using Mount option I have attached silver Container to DataBricks this time, I have performed aggregrations, business level transformations and saved the same as a delta format in Gold Layer.
Finally, I have mounted the data onto Synapse Analytics used Serverless SQL pool to attach the data from Synapse Analytics to PowerBI.
I would have used a Dedicated pool but since we are not performing any operations and using Synapse analytics just as a medium to connect to PowerBI, I have used serverless pool.
in PowerBI I have performed some more final cleaning, aggregrations, caluclated columns and DAX as required by the Business team to show metrics and KPIs for the business.
