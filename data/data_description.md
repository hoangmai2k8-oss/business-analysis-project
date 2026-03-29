# Data Description
## Dataset Used
The dataset used for this project is Sales.
## Source
Data was retrieved from:
The table can be accessed through google bigquery
- Website: [https://console.cloud.google.com/bigquery?ws=!1m5!1m4!4m3!1sproject-c3127232-fd88-4b58-a7f!2sassignment!3ssales]
## Retrieval Instructions
1. Go to the source link
2. Open the BigQuery page in the Google Cloud console.
3. In the Explorer pane, expand your project, dataset, and select the table Sales.
4. In the details pane, click the Export option, then select Export to GCS.
5. In the "Export to Google Cloud Storage" dialog:
    gs://data/assignment/sales.csv
    For Export format, choose CSV format.

6. Click Export to start the job.
7. Open the Cloud Storage browser in the Google Cloud console. Navigate to the bucket and folder where you exported the data. Click the download icon next to the file(s) to save them to your computer.
