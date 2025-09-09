# Exercise 3 - Install Intelligent Applications

In this exercise, we will walk through how to install intelligent applications in SAP BDC.

What is an SAP Business Data Cloud Intelligent Applications?

SAP Business Data Cloud Intelligent Applications are a suite of adaptive and AI-powered applications that learn from your
data, understand business context, and act on your behalf to transform business outcomes. These are fully managed, built
on a foundation of SAP data products, and incorporate pre-defined metrics, AI models, and planning capabilities,
simplifying how you connect and integrate every part of your business.
They are fully managed applications that are installed through the BDC Cockpit. Once installed, the associated data products, data models, analytics and application assets are deployed and configured automatically. The
prebuilt SAP managed data products installed with the intelligent application packages can then be utilized to build new
insights and develop AI faster.

## Exercise 3.1 Intelligent Application Overview - Working Capital Insights

As an Admin of BDC, installing one or more intelligent applications is normally the first task you will do after completing BDC provision. In this exercise, let us first locate available intelligent applications, look at the details of one of these intelligent applications called the **Working Capital Insights** so that we can start using the insights and the underlying data products to their full potential.

Following illustration gives an impression of the look and feel of this intelligent application:<br/><br/>
![WCI_A_Overview](images/WCI_A_Overview.png) 

1. Log in to your BDC cockpit

2. Open the **Intelligent Applications and Data Packages** module in SAP Business Data Cloud. 
![IA_AvailablePackages1](images/IA_AvailablePackages1.png) 

3. This module shows the **Working Capital Insights** Intelligent Application which is available for installation. You can also search for the same in the search bar above.
![IA_AvaiablePackagesWCI](images/IA_AvaiablePackagesWCI.png)


This intelligent application is powered by the data from S/4 PCE data products, SAP Datasphere models and SAP Analytics Cloud stories. All of this is comprised in the **Details** section of the intelligent application.
1. Data Products: As shown in the following image, the intelligent application is powered by data from 35 data products, which are highly curated datasets with rich semantic purpose.
![dataProducts](images/dataProductsComprised.png) 

2. Content:
- SAP Analytics Cloud: The stories that are comprised in this intelligent application will be created in SAC in a folder called SAP_SAC_WCI. You can find this under the Files > Intelligent Applications > SAP S/4HANA > Finance tab. This folder is SAP-managed and will be read-only. 

- SAP Datasphere: The installation creates and deploys three spaces in the underlying SAP Datasphere. 
    * SAP_WCI - This space contains all the analytic models that form the foundation of the SAC stories.
    * SAP_S4H - This space contains all the modelling artifacts required to build the analytic models, such as views, data access controls etc.
    * SAP_S4H_ING - This space contains all the local tables and their corresponding replication flows. The data from the data products reside in these local tables.  <br/>



## Exercise 3.2 Install Intelligent Application - Working Capital Insights

Now we have checked the details of Working Capital Insights intelligent apps and make sure this is the intelligent app we want to install. In this exercise, let us look at the steps of installing the intelligent application.

Due to the technical and time limitations, we will use guided tours for activities in this class which takes long time and affect the whole shared landscape.

Guided tour is a pre-built, step-by-step interactive walkthrough within a product's demo environment, using tooltips, clear instructions, and highlighted features to lead prospects through key workflows and functionalities.

Start the tour [here](https://tour-viewer.platform.saleo.io/adc38a87-3653-488b-9999-a3f05e4b9360).


### Explaination: Install Intelligent Applications


1. In the **Working Capital Insights** homepage, choose the 'Install' button to kick off the installation. A dialog opens up to confirm the installation details. Choose 'Install' again to confirm.
![IA_InstallOptions%20WCI](images/IA_InstallOptionsWCI.png)
> [!NOTE]
> This saves the related content in an SAP-Managed spaces in SAP Datasphere (DSP) and an SAP-Managed folder in SAP Analytics Cloud (SAC).

> [!IMPORTANT]
> SAP Business Data Cloud uses a singleton SAP Business Data Cloud Cockpit to govern multiple formations. One cockpit can be used to install intelligent applications and packages in different environments, for example, dev, test and prod. Hence, during installation it is asked to specify which source system supplies the data to fuel the intelligent application and which SAP Datasphere & SAP Analytics Cloud constellation is used for the installation. Source System and Install Location must be specified.

2. The status of the installation changes to 'Installing' and then 'Active' when the installation has finished. 
![IA_InstallingWCI](images/IA_InstallingWCI.png)

3. After installation you will find **Working Capital Insights** under the Installed Apps and Packages.
![IA_InstalledWCI](images/IA_InstalledWCI.png)
> [!NOTE]
> This step can take from several minutes to a few hours, because the step also entails fetching all the underlying data products data into the storage and semantic layer of BDC.

4. To view the content in SAP Datasphere, you can open it from the System Landscape Tab by navigating from the relavant formation.

5. In the **Security> Roles** tab, two new scoped roles have been created on installation of the Intelligent Application. The scoped roles have the newly created spaces `SAP_S4H`, `SAP_WCI` and `SAP_S4H_ING` as the scopes. The two newly generated scoped roles are `BDC_Scope_Space_Admin` and `BDC_Scope_Consumer`.
![IA_Role2](images/IA_ScopedRole2.png)<br/>
![IA_Role2](images/IA_ScopedRole4.png)<br/>
> [!NOTE]
> The scoped role `BDC_Scope_Consumer` needs to be assigned to the users if they want to see data in the SAP Analytics Cloud story.

6. In **Space Management**, navigate to each of these spaces and assign users to the two above mentioned scoped roles.
![IA_AddUsersToScopedRoles](images/IA_AddUsersToScopedRole.png)<br/>
![IA_AddScopesToUsers](images/IA_AddScopesToUsers.png)<br/>


7. To maintain Data Access Control for the installed Intelligent Application, open the Data Builder and open the `Central Permissions Table` in the space `SAP_S4H`. You can upload the permissions in the form of a CSV file. For a sample CSV file, please refer to the format [here](other/WciAuthorizationList_set.csv) <br/>
![IA_EditDAC](images/IA_Dac1.png)<br/>
![IA_EditDACUsers](images/IA_Dac2.png)<br/>

    - Explanation:
    If the Data Access Control is not properly populated, the users will not be able to see any data (that is, in the data preview in SAP Datasphere, or in Story consumption). Let us take a deeper look into this CSV file. There are 12 rows governing 12 criterion. If five users need access, then the e-mail addresses of all five users must be repeated with each of these 12 criterion. That is, 5*12 rows where the column `User_Id` will contain the user's email address. The names of the columns or criterion cannot be changed and must be uploaded accurately.

8. On installation, the replication flows fetch the data in the local tables. However, for the data to be populated in the views, the task chains and the corresponding transformation flows need to be run. Before running the task chains, grant yourself access to do so, as follows.
![IA_AuthorizeTaskChain](images/IA_AuthorizeTaskChain.png)<br/>

9. In the space, `SAP_S4H`, there are two task chains. Run both task chains as follows:
  - Run task chain sap.s4h.TC_InitWCIConfiguration 
  - Configure the sap.s4h.IL_FinancialDataModelConfiguration table with G/L Account Hierarchy
  - Run task chain sap.s4h.TC_NWCPersis
  - You can find more information [here](https://help.sap.com/docs/business-data-cloud/viewing-insight-apps/2fe6d4074470414585326125c2661428.html)

![IA_AuthorizeTaskChain](images/IA_TwoTaskChains.png)<br/>
![IA_TaskChainRun](images/IA_TaskChainRun.png)<br/>

10. The task chain runs can be monitored from the **Data Integration Monitor** > **Task Chains** tab.
![IA_MonitorTaskChains](images/IA_MonitorTaskChains.png)<br/>
> [!NOTE]
> If running either of these task chains results in an OutOfMemory exception, refer to the following recommendations. In the **System > Configuration > Workload Management** tab, change the setting of the two spaces `SAP_S4H` and `SAP_S4H_ING` to custom, as shown in the following image. <br/> ![IA_taskChainConfig](images/IA_taskChainConfig.png)<br/>


11. To run all the transformation flows, open the space `SAP_S4H` in Data Builder and navigate to the **Flows** tab. There are five transformation flows that have to be run. <br/>
![IA_OpenSAC](images/IA_TF_list.png)<br/>

12. Open and run each of the Transformation Flows.<br/>
![IA_RunTf](images/IA_RunTf.png)<br/>

13. The transformation flow runs can be monitored from the **Data Integration Monitor** > **Flows** tab.
![IA_RunTf](images/IA_RunTf.png)<br/><br/>
![IA_MonitorTf](images/IA_MonitorTf.png)<br/>

14. Next, we have to manage the access in SAP Analytics Cloud. Open SAP Analytics Cloud using the Product Switch button. In SAC, in the **Security>Users** tab, add all the relevant users who will need access to content in SAC and so that the content can be shared with them.
    
> [!NOTE]
> An admin role, like **BI Admin** or **Admin**, is required to view the Intelligent Applications tab. Hence, for sharing the intelligent application story for the first time, one of these admin roles is required. For subsequent users, the intelligent application can be shared with them as shown in the following steps.
![IA_AddSACUsers](images/IA_AddSACUsers.png)<br/>

15. From the Managed content folder in the file repository, grant the access rights to all relevant users. Go to Files > Intelligent Applications > SAP S/4HANA > Finance 
![IA_ShareSACContent](images/IA_ShareSACContent.png)<br/>
![IA_ShareSACContentUsers](images/IA_ShareSACContentUsers.png)<br/>

**Working Capital Insights** Intelligent Application is now available for consumption.

## Updating the Intelligent Application
Please refer to this collection [SAP Note](https://me.sap.com/notes/3606495) for all updates related to Working Capital Insights.



## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
