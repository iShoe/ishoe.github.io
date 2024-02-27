---
title: "Twitter Analytics Microservice"
excerpt: "A RESTful service on EKS and with data on AWS RDS to find interaction score between two users and most used phrases on Twitter. Implemented horizontal scaling, connection pooling, and concurrency for maximizing RPS."
collection: projects
---

* Deployed RESTful service on EKS to find interaction score between any two users and most used phases on Twitter using Golang and fasthttp framework.
* Performed ETL on over 1TB of twitter dataset and loaded the data into AWS RDS Aurora cluster with optimized schema. 
* Implemented pod replication, horizontal scaling, connection pooling, concurrency for maximum RPS.
Achieved over 30k RPS with a budget of  1.197$ per hour. 
