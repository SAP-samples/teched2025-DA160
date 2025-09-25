# Exercise 7- Customization of Intelligent Application - Data Access Control

In the previous exercise, we saw how the SAP BDC Admin persona creates the custom-managed version of the Intelligent Application `Working Capital Insights`. In this exercise, we will see how the Data Access Control can be configured in the custom-managed version of the Intelligent Application.

The relational modelling entities or the reuse entities of `Working Capital Insights` are contained in the Datasphere space `SAP_S4H`. As you know, this is an SAP-managed space. Row-level security for the Intelligent Application is also configured in this space. 

In this exercise you will learn how to maintain the Data Access Control centrally for all the Intelligent Applications for each LOB Application. In this example, we are considering 
`Working Capital Insights`.

## Exercise 7.1 Guided Tour: Maintain Data Access Control centrally for S/4HANA PCE
Due to the technical and time limitations, we will use guided tours for activities that are one-time.

The following guided tour will show you how the data access control is maintained in the S/4HANA reuse space. All the dimensions within `Working Capital Insights` must have the row-level security maintained.

Start the tour [here](https://tour-viewer.platform.saleo.io/b8a59936-3d02-4f1f-a4e9-13b322bfa18d). Explanations are provided below to help you understand the exercise.

### Explanations: 

All intelligent applications delivered through SAP Business Data Cloud are secured through data access controls. By default, no user can view any data presented in the provided SAP Analytics Cloud stories. To make data available to the users authorized to see it, you must upload your authorizations to the provided permissions table.

When data is delivered to SAP Datasphere through SAP Business Data Cloud, any authorizations that are applied to the data in the source system are not imported.

1. In your preparation space `SAP_S4H`, identify the fact views and the permissions table.
2. Prepare your permissions records in the operator and values format to provide row-level access to the data in your facts.
3. Upload the appropriately formatted operator and values permissions data as a CSV file.
4. You can also maintain permissions data manually using the data editor .
5. Maintain the permissions table as necessary.

## Summary

You've now learned how to maintain row-level security in SAP BDC for an Intelligent Application.

## Conclusion

This was the last exercise in this practical walkthrough for SAP BDC. Happy Learning!