# Getting Started

Welcome to DA160 - SAP Business Data Cloud from Setup to Streamline: Practical Walkthrough.

In this exercise, you will explore the BDC's core components, learn how to activate and manage them, and practice strategies to streamline data integration, governance, and access.

In order to proceed effectively with the subsequent exercise, Let's first review some basic information regarding SAP Business Data Cloud. 


## What is SAP Business Data Cloud?

SAP Business Data Cloud is a fully managed SaaS solution that unifies and governs all SAP data and seamlessly connects with third-party data—giving line-of-business leaders context to make even more impactful decisions. Built as part of SAP’s broader data and analytics strategy, BDC is designed to bring together both SAP and non-SAP data sources into a single, trusted environment. By harmonizing enterprise data and embedding governance frameworks, it ensures accuracy, consistency, and compliance, thereby reducing the risks often associated with fragmented data landscapes.

SAP Business Data Cloud was launched at SAP Business Unleashed on Feb 13, 2025, and is now generally available.

## What are the core components of SAP Business Data Cloud formation?

A formation is used to connect a group of application tenants together into a virtual BDC landscape. Formations allow you to combine SAP solution systems to simplify the connectivity setup and to provide a unified view of all components required for the implementation.

Every SAP BDC Formation must (can) include:
- One SAP Business Data Cloud Cockpit
- One or more S/4HANA PCE systems
- Zero or one SAP Datasphere
- Zero or one SAP Analytics Cloud
- Zero or one SAP Databricks


### SAP Business Data Cloud Cockpit:

A unified management interface for administering BDC: browse/install Intelligent Apps, manage data products, monitor integrations (e.g., with Databricks), and oversee system health.

### S/4HANA Private Cloud Edition System:

SAP S/4HANA plays a significant role in the SAP Business Data Cloud (BDC) ecosystem, primarily as a source of enterprise data that can be leveraged for advanced analytics and business intelligence. 

### SAP Datasphere:

Functions as the data integration and modeling layer, provides a unified semantic model with governance, enabling users to work in business terms rather than raw data tables.

### SAP Analytics Cloud:

Delivers analytics, reporting, dashboards, and enterprise planning—all in one platform—facilitating interactive insights and scenario modeling.

### SAP Databricks:

Brings advanced AI, machine learning, and data science capabilities by enabling seamless access to SAP and third-party data without complex data replication.

### Neetha to add about BW?
??***** In future, also SAP BW Private Cloud Edition (BW PCE) tenants can be provisioned but for the time being,
there’s no self-service and customers need to reach out to SAP to get a tenant provisioned. 

## Exercise Overview
The exercises are structured by SAP Business Data Cloud end-user personas. For each persona, there are a sequencial exercises to perform. It describes responsibilities of the different personas that range from business users to system administrators


## Summary

Now that you have a good understanding of the exercises, lets get started with the first exercise.

Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
