---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# Building a Data Lake with Amazon S3 and Amazon Athena

A data lake is a centralized storage architecture that lets you keep raw data in any format — structured, semi-structured, or unstructured — until you're ready to use it. On AWS, this architecture can be implemented effectively using Amazon S3 as the storage layer, AWS Glue for metadata management, and Amazon Athena for querying data with SQL without managing any infrastructure.

![Data Lake architecture with Amazon S3 and Amazon Athena](/images/blogs/blog3.jpeg)

## Key Takeaways

* Amazon S3 serves as the core storage layer of the data lake: S3 offers low-cost storage, high durability, and near-unlimited scalability, making it well suited to ingesting raw data from varied sources such as applications, IoT devices, system logs, or streaming data.
* AWS Glue manages metadata through its Data Catalog: Glue Crawler automatically scans data in S3, detects its schema, and registers that information in the Glue Data Catalog, allowing services like Athena to understand and query the data accurately.
* Amazon Athena runs SQL queries directly against data in S3: it's a serverless query service that uses the Presto engine to execute SQL directly on data stored in S3, with no need to load it into a separate database, and it's billed only by the amount of data scanned.
* Partitioning the data optimizes both performance and cost: organizing data in S3 using a partition structure (e.g., by year, month, day) lets Athena scan only the relevant portion of data, cutting query time and cost significantly.
* Storage format has a major impact on query speed: using columnar formats like Parquet or ORC instead of CSV or JSON noticeably improves read performance and reduces the amount of data scanned per query.
* A fully serverless, easily extensible architecture: the entire pipeline — from ingestion to storage to querying — requires no server management, and it integrates smoothly with Amazon QuickSight for data visualization or Amazon SageMaker for machine learning use cases.

This S3/Glue/Athena data lake architecture on AWS is especially well suited to organizations that want to build a cost-efficient, highly scalable data analytics platform without investing in complex infrastructure. It's also an ideal foundation for future advanced analytics, business intelligence, or machine learning initiatives.

[View the post on AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203134240451536/?rdid=6V3UDKT1qdleFAkb&share_url=https%3A%2F%2Fwww.facebook.com%2Fshare%2Fp%2F1Bn86KFzSx%2F%3F_rdc%3D1%26_rdr)

---

## References

* [Amazon Athena – AWS Documentation](https://docs.aws.amazon.com/athena/latest/ug/what-is.html)
* [AWS Glue – AWS Documentation](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html)
* [Data Lakes and Analytics on AWS](https://aws.amazon.com/big-data/datalakes-and-analytics/)