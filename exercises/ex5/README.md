# Exercise 5 - Share Data Product with Databricks

In this exercise, we will learn steps how Data products in SAP Business Data Cloud are shared with Databricks. 

At SAP Business Unleashed 2025, we announced SAP Databricks, a landmark partnership that brings the power of
Databricks directly into SAP Business Data Cloud.

What is SAP Databricks?
SAP Databricks is an SAP-managed OEM version of the Databricks Data Intelligence Platform embedded natively within
SAP Business Data Cloud. SAP Databricks brings industry-leading AI/ML, data science, and data engineering capabilities
together with semantically rich, business-ready data from SAP applications. 

When a data scientist identified a potential useful data product in the Catalog, the Admin need to share this data product in BDC to Databricks, allowing data scientist to consume and further explore the potentials of this data prodcut in Databricks.  

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
