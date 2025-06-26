# **Project Description**
UCW Finance Operation team wants to know the patterns in delayed payments that affect cashflow. We go throught Payment Records, Invoice Details and Customer Profiles to analyze payment behavior and identify causes of payment delays impacting cash flow. We created a DAP (Data Analitic Platform).

## **Metodology**
This project was developed using three steps: Analysis, Design and Implementation.

### **1. Analysis**
In this step we review the root cause of this problem where we could identified some causes related to our main problem:

![fishbone](./images/analysis/fishbone.png "Fishbone diagram")

After that, we reviewed the datasets that is close related to our problem: 

![dataset-description](./images/analysis/dataset-description.png "Dataset Description")

The dataset includes transactional data from UCW Finance Operation Team over the past years, containing the following key features:

- **Payment Records:**
    - **PaymentID:** Unique identifier for each payment
    - **CustomerID:** Identification number for each customer
    - **InvoiceID:** Identification number for each invoice
    - **PaymentDate:** Date the transaction
    - **AmountPaid:** Amount paid in the transaction

- **Invoice Details:**
    - **InvoiceID:** Identification number for each invoice
    - **CustomerID:** Identification number for each customer
    - **InvoiceDate:** Date the invoice
    - **DueDate:** Due date of the invoice
    - **TotalAmount:** Total amount of the invoice

- **Customer Profiles:**
    - **CustomerID:** Identification number for each customer
    - **CustomerName:** Firstname and lastname of the customer
    - **CreditTerms:** It contains information about credit terms like *Due on Receipt, Net 30 or Net 60*

It time to see how we plan to clean our dataset:

![dataset-cleaning](./images/analysis/dataset-cleaning.png "Dataset Cleaning")

Final step for analysis is enrich our dataset:

![dataset-enrich](./images/analysis/enrichment.png "Dataset Enrich")

### **2. Design**
In this step we design our solution for building our DAP. First we have to design our datalake for our dataset:

![datalake](./images/design/datalake.png "Datalake")

It is time to design our DAP architecture to store, clean and enrich our datasets. We planned to use these services:

![solution](./images/design/architecture.png "Solution")

### **3. Implementation**
We started creating our buckets in S3 called *finance-raw-elthon*, for our raw datasets and one folder for each dataset:

![bucket-raw-dataset](./images/implementation/s3-raw.png "Raw Dataset")

Next, we created some projects in AWS Glue Databrew to clean each dataset:

![databrew-projects](./images/implementation/cleaning/databrew-projects.png "AWS Glue Databrew Projects")

Besides, we created one cleaning job for each dataset:

![databrew-cleaning-jobs](./images/implementation/cleaning/databrew-cleaning-jobs.png "Cleaning Jobs")

To store our cleaned dataset, we created a new bucket called *finance-cln-elthon*.

**Payment Records:**

We also create a profiling job to load and analyze the payment record dataset:

![pym-rec-profiling-job](./images/implementation/cleaning/databrew-payment-records-job1.png "Payment Records - Profiling Job")

And these were the results after running the profiling and cleaning jobs:

![databrew-cleaning-pay-rec-output1](./images/implementation/cleaning/databrew-payment-records-output1.png "Payment Records - Output 1")

![databrew-cleaning-pay-rec-output2](./images/implementation/cleaning/databrew-payment-records-output2.png "Payment Records - Output 2")

![databrew-cleaning-pay-rec-output3](./images/implementation/cleaning/databrew-payment-records-output3.png "Payment Records - Output 3")

![databrew-cleaning-pay-rec-output4](./images/implementation/cleaning/databrew-payment-records-output4.png "Payment Records - Output 4")

**Invoice Details:**

**Customer Profiles:**


## **Tools and Technologies**
    
## **Cloud Foundation**
