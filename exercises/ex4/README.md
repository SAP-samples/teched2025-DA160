# Exercise 4 - Activate Data Package and Install Data Products

In this exercise, we will learn how to activate a Data Package in SAP Business Data Cloud cockpit and then install the included Data Products in the corresponding SAP Datasphere tenant. But before we do that, let's take a closer look at what a Data Package is and its key elements.

### What is a Data Package? 
A Data package contains sets of related data products for use in modelling projects and pro-code applications. All Data packages are available in the SAP Business Data Cloud Cockpit in the [Catalog & Marketplace](#explore-data-products-in-the-catalog).

The activation of a Data Package in SAP BDC Cockpit is a prerequisite to make it available for business users in the Catalog. The Data Products of this package are visible in the Catalog after this activation. They can be either shared with Databricks for AI/ML use cases or installed in SAP Datasphere which is required for modeling in SAP Datasphere.

## Exercise 4.1 Activate Data Pacakge

1. Log into the SAP Business Data Cloud Cockpit.
<img src="./images/BDCCockpit_login.png"  width="1000"/>

2. In the cockpit, open the tab **Insight Applications and Data Packages**. This tab shows all the Intelligent Applications and Data Packages that are available for installation. <br/>
<img src="./images/insight_apps_data_packages.png"  width="1000"/>

3. Search for the Data Package that you want to activate. In this exercise, we will activate the **SAP S/4HANA Financial Operations Data Products**. This data package is available for activation and includes two data products. 
<img src="./images/DataPackage_screen.png"  width="1000"/>

#### Overview
The Overview section provides the following information about the package:
<img src="./images/BDCDatapackage.png"  width="1000"/>


- Activate: Activation of a Data Package in SAP BDC Cockpit is a prerequisite to make it available for business users in the Catalog (covered in this exercise). Deactivation can also be performed here which is currently represented in this example. 

- Category : categories help in organizing and filtering data efficiently, ensuring that users can easily find relevant information related to specific areas like finance or sales.

- Version: Displays the version of the data package.

- Source System: Displays the SAP S/4HANA Cloud Private Edition system that provides the business data which populate the data products.

- Last Modified : Displays the date on which the data package was activated or last modified (appears for active data packages).

- Minimum System Version: This column appears for available data packages only and displays the minimum version of the SAP S/4HANA Cloud Private Edition system required for the data package to be installed. If the current SAP S/4HANA Cloud Private Edition version included in your 'SAP Business Data Cloud' formation is lower than the minimum version required by the data product, the data product cannot be installed.

- System Version: Appears for activated data packages and displays the current version of the SAP S/4HANA Cloud Private Edition system.

- Update: if there are updates available, they will also be shown at the data package level, and you could trigger an update.

> [!IMPORTANT]
When activating a data package, make sure the source system is correctly identified and accessible. Check that the source system's version meets or exceeds the minimum required by each data product in the package. Data products will only activate if their minimum version requirements are met. For example, if one product requires version 2021 and another requires 2025, and your S4 system is on version 2024, only the product requiring version 2021 will activate. Additionally, the data package itself may have a minimum version requirement; if the source system doesn't meet this, no data products will install. The installation of data products can be partial or full based on the source system's version compatibility.

Due to the technical and time limitations, we will use guided tours for activities in this class which takes long time and affect the whole shared landscape.

Guided tour is a pre-built, step-by-step interactive walkthrough within a product's demo environment, using tooltips, clear instructions, and highlighted features to lead prospects through key workflows and functionalities.

Start the tour [here](https://tour-viewer.platform.saleo.io/dd7619a5-ef6b-49b6-84d0-f6bac8477db9).

### Explainations

4. Click on ***Activate*** to start the installation process. You will be asked to select the source system. Activating the Data Package will make the Data Products available in the Catalog. :wrench: <br/>
<img src="./images/Datapackage_sourcesystem.png"  width="1000"/>
 

5. The status changes to **Activating**. This takes some time depending on the volume of the data in the underlying source system. SAP Business Data Cloud takes care of the data extraction and processing in the background. Once, the activation completes, the Data Products that are comprised in this Data Package are available for consumption. :wrench:<br/>
<img src="./images/Datapackageactivation_screen.png"  width="1000"/>

6. The Data package and the Data Product comprised in it is now **Active**,if there are updates available, they will also be shown at the data package level, and you could trigger an update. 
<img src = "./images/DataPackage_active.png" width= "1000"/>

7. After installation of the data package **SAP S/4HANA Financial Operations Data Products**, you will find under the **Installed** tab in Intelligent Applications and Data Packages.
<img src = "./images/Insightappandpackage_active.png" width= "1000"/>

8. Select the tab named  ***SAP Business Data Cloud Data Products***. You see all Data Products available. In the Catalog screen, under the tab SAP Business Data Cloud Data Products tab, you can find all the data products that can be now installed in the consumption spaces in SAP Datasphere. They cannot be installed from here. This is just for exploration and sharing with DBX.
<img src="./images/catalog_bdc.png"  width="1000"/>



## Exercise 4.2 Install Data Products

> [!Note]
> The Data Product needs to be installed from SAP Datasphere Catalog once its corresponding Data package has been activated in Business Data Cloud Cockpit. Data product can be directly shared to Databricks through SAP BDC cockpit if Databricks is part of the formation.


1. To install the Data Product in SAP Datasphere, switch to SAP Datasphere through  **System Landscape** Tab by navigating from the relavant formation.
<img src ="./images/SwitchDatasphere.png"  width="1000"/>.



> :books: If you are participating in a SAP BDC training, the step 2 has already been completed by the trainers, as it requires admin roles. Please continue with step 3.

2. Before installing the Data Product, we need to add the custom space where we want to install our required Data product to the System > Business Data Products tab and select the correct source system.  Follow these steps for your custom space(consumption space) where the data product will be installed:

- Navigate to the **System** menu.
- Select the **Business Data Products** tab.
- Add the custom space where you intend to install the Data Product.
- Ensure that you select the correct source system for accurate integration.

<img src="./images/AddCustomspace.png"  width="1000"/>


3.In the Catalog & Marketplace **SAP Business Data Cloud Data Products** tab search for the Data Product ***House Bank*** which was already activated in the BDC Cockpit. <br/>
<img src="./images/DatasphereCatalog.png"  width="1000"/>


4.Open the Data Product ***House Bank***.
<img src="./images/HouseBank.png"  width="1000"/>

5.This data product is active as displayed in the header. 
<img src="./images/InstallDataProduct.png"  width="1000"/>

6.Choose the 'Install' button to start the installation. 
<img src="./images/InstallScreen.png"  width="1000"/>

7.Select target space **Custom Space**, and click on ***Next Steps***.
<img src="./images/Selecttarget.png"  width="1000"/>

8.Review the entities (replication flow and local table) and run the import selecting ***Start Import and Deploy***. <br>
<img src="./images/ImportEntities.png"  width="1000"/> 

9.You see the message ***Importing entities. Check the notifications for the status of the import.***.

10.Notifications display that the import started and also that the import completed successfully.

<img src="./images/import_completed.png"  width="1000"/>



>[!Note]
>When you install a Data Product in SAP Datasphere, it sets up and deploys entities in an ingestion space or an SAP-managed space. Importantly, this does not create a second copy of the data. Instead, it shares the data from the ingestion space. This space is created when the first data product for the application instance is installed into DSP, either by a customer installing the data product in DSP or through the successful installation of an Intelligent Application. This approach ensures efficient resource use and keeps the data accurate and centralized.
><img src="./images/SAPManagedSpace.png"  width="1000"/>


11.In your assigned space, create a new **Graphical view** for Datapreview.

><img src="./images/GraphicalView.png"  width="1000"/>

12.Drag the table ***Master Data For House Bank*** into the view and save it as ***HouseBank_DataPreview***

><img src="./images/HouseBank_DataPreview_view.png"  width="1000"/>

13.Preview the data in the ***HouseBank_DataPreview*** view.

><img src="./images/Datapreview_View.png"  width="1000"/>

>`[Note]
As the table Master Data For ***House Bank*** is shared from the SAP-managed space. The table is automatically populated by the Replication Flow, so you don't need to manually start a run. 

You can now enhance the business use case by building on top of the installed data product.



## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
