# ETL-Pipelining with Airflow, Google Cloud Storage and BigQuery
Implementing an ETL Pipeline Using Big Query and Airflow for Covid-19 Data


## **Architecture Overview**
![architecture](results/system_architecture.jpg)

## **Data Sources**
1. Kaggle
2. Comma separated values (CSV)
3. Excel (xls, xlsx)
4. JSON

## **Tech Stacks**
1. Python (v3.8.5)
2. Apache Airflow (v2.5.0)
3. Google Cloud Storage (GCS)
4. Google BigQuery
5. Google Composer

## **Installation Setup**
### Setup the Computing Environment
**Step 01: - Go and create a free account on Google Cloud Platform (GCP). Once logged in click on the console it will take you in and post that go to google Composer to setup the environment for the project**

![GCP](results/step01.png)

**Step 02: - Once entered into google composer it will look something like this.**

![Google Composer](results/step02.png)

**Step 03: - Post that go to create environment and select Composer 2 with autoscaling option with airflow 2 which provides better performance.**

![Composer 2 and Airflow Setup](results/step03.png)


**Step 04: - Once entered into the creation phase select all the default values for everything and select the smaller environment size and then finally click on create environment.**

![Environment Configuration](results/step04.png)
**

**Step 05: - Selecting the appropriate environment size**

![Environment Settings](results/step05.png)


**Step 06: - Selecting the appropriate network configuration and other defaults and finally create the environment. It takes a while for it to be created so we have to wait a bit but once it creates it has everything, the Airflow, The Webserver and the dag folders to execute the ETL pipeline. Please also find below the reference link for the installation steps:**

![Final Setup](results/step06.png)

**Cloud Composer documentation. (n.d.). Google Cloud. **

https://cloud.google.com/composer/docs

### BigQuery Schema Snapshots

**1. Staging Schema:-**

 ![Final Setup](results/staging.png)

**2. Preprocessed Table Schema:-**

 ![Final Setup](results/preprocessed_table.png)

**3. Processed Table Schema:-**

 ![Final Setup](results/processed_table.png)

   ### Google Cloud Storage Setup
1. Back to your GCP console, choose Cloud Storage. You can find it on **Storage > Cloud Storage**
2. Click `CREATE BUCKET` button. Then fill some fields such as:
   - Name your bucket (example: blank-space-de-batch1)
   - Choose where to store your data
     - I would suggest to choose **Region** option because it offers lowest latency and single region. But if you want to get high availability you may consider to choose other location type options.
     - Then choose nearest location from you
   - Leave default for the rest of fields.
3. Click `CREATE`
4. Your bucket will be created and showed on GCS Browser
    ![Successful Bucket Creation](results/bucket.png)
<br><br>


## Results
- This is Training Model Schema:-
 ![Training Model Schema](results/training_schema.png)

- Prediction Schema:-
![Prediction Schema](results/prediction_schema.png)

- Staging Table Output
  ![Prediction Schema](results/bucket.png)

 -Preprocessed Table Output
 ![Prediction Schema](results/bucket.png)

 - Processed Table Output
   ![Prediction Schema](results/bucket.png)

  - ETL Pipeline
    ![Prediction Schema](results/bucket.png)

   - Training Model
     ![Prediction Schema](results/bucket.png)

     - Evaluation Model
       ![Prediction Schema](results/bucket.png)

       - Predictions
         ![Prediction Schema](results/bucket.png)

         - Final Prediction Visualization Report
           ![Prediction Schema](results/bucket.png)



- The result of loaded table in Data Warehouse which using BigQuery
![loaded-table-bq](images/Final%20Result%20Data%20on%20BigQuery.png)


## How to Use
Everytime you want to run *Native Airflow* on your computer. Do this: 
1. Activate your virtual environment by executing `source venv/bin/activate`
2. Run `airflow webserver --port 8080 ` at your current terminal
3. Run `airflow scheduler` on your other terminal.
4. Go to http://localhost:8080 
