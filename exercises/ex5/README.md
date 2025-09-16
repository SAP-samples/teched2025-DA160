# Exercise 5 - Enhance the Data Product in Databricks and Install enhanced Data Product back to Datasphere

In Exercise 4, we have shared the **Company Code** Data product from SAP BDC cockpit to SAP Databricks. The Data scientist can start working on this data product. 

In this exercise, we will simulate the process of exploring the Data Product in SAP Databricks, and install the enhanced data product to Datasphere so that data analyst can start modeling in Datasphere. 

## Exercise 5.1 Hands-on: Enhance the Data Product in Databricks

Let's first do some enhancements on the **Company Code** Data product which was shared to you previously.

1. Log in to your BDC cockpit, using the link and username/password provided. Go to the **System Landscape** tab, locate URL of SAP Databricks, click the URL of Databricks.
![locatedatabricks](images/0501-locatedatabricks.png) 

2. Provide Email and select Continue. The email is the username@sapexperienceacademy.com. 
![logindatabricks](images/0502-dblogin.png) 

3. Select Continue with SSO.
![logindatabricks](images/0503-dbsso.png) 

4. Select the default workspace to continue.
![wpdatabricks](images/0504-dbworkspace.png) 

5. You have enter the welcome page of SAP Databricks.

At SAP Business Unleashed 2025, we announced SAP Databricks, a landmark partnership that brings the power of
Databricks directly into SAP Business Data Cloud.

What is SAP Databricks?

SAP Databricks is an SAP-managed OEM version of the Databricks Data Intelligence Platform embedded natively within
SAP Business Data Cloud. SAP Databricks brings industry-leading AI/ML, data science, and data engineering capabilities
together with semantically rich, business-ready data from SAP applications. 

Now let's locate the **CompanyCode** data product which has been shared to you in ex4.

6. Go to **Catalog** tab and locate the **Company Code** Data product as inllustrated in the figure below. This Data Product was shared from the SAP Business Data Cloud to SAP Databricks and it’s available for consumption.

![ccdatabricks](images/0505-dbcompanycode.png) 

7. Now the data scientist can start working on this data. Due to the time limitation, we won't include the reprocessing exercise in our session. Instead, we will show you the reprocessed data so that we can continue. Let's expand the catalog again, go to **My organization** and follow the path illustrated below:

![ccdatabricks](images/0506-dbenhance.png) 

We enhanced this data product by applying a Clustering ML algorithm to the original dataset. The output contains the clustering coordinates and labels for each Company Code.

8. 

## Exercise 2.1 Sub Exercise 1 Description

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
