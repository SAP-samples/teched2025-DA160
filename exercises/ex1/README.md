# Exercise 1 - Provision BDC via SAP for Me

When you as a customer subscribes to BDC, you will use SAP for Me to provision a BDC tenant. 
You will need the following to perform this activity in the real-world case:
- An SAP for Me account
- Successful purchase of the SAP Business Data Cloud product and the corresponding entitlements

Due to the technical and time limitations, we will use guided tours for activities in this class which takes long time and affect the whole shared landscape.

Guided tour is a pre-built, step-by-step interactive walkthrough within a product's demo environment, using tooltips, clear instructions, and highlighted features to lead prospects through key workflows and functionalities. When accessing a guided tour, please click the highlighted area to proceed to the next step.

## Exercise 1.1 Guided Tour: Configure SAP Business Data Cloud in SAP for Me

Access the guided tour and follow the steps in SAP for Me.
During the guided tour, you will:

- Provision SAP Datasphere
- Provision SAP Analytics Cloud
- Create Formation and include systems
- Provision and include SAP Databricks

Start the tour [here](https://tour-viewer.platform.saleo.io/0e902660-fbc8-4d3f-888d-2470b23a80d3). Explainations are provided below to help you understand the exercise.

### Explainations: 
1. In the SAP for Me account, under the **Portfolio & Products** Tab, under **My product suite** section, the tile **SAP Business Data Cloud** tile is visible since the product has been purchased and the commercial entitlement for SAP Business Data Cloud also exists in your URM organization. By clicking it, you can explore all the technical entitlements, also known as Eligibilities. that is, the set of eligible applications that are part of the BDC product.

<img src="images/sap4me-images/sap4me-entry.png" alt="internalHost" width="1500"/><br/>

2. You can go through the **Applications**, **Solutions**,**Resources** and **Customer Landscape** tabs to check the details of your BDC.

#### Provisioning of SAP Datasphere
In a SAP Business Data Cloud Landscape, other than the data source systems, other products can be provisioned to leverage the different capabilities that are provided.
SAP Analytics Cloud serves as the consumption layer where the intelligent applications reside which are powered by the underlying data products.
SAP Datasphere is the runtime where the data products can be installed and then enhanced.

Let's see how we can provision these systems by looking at the example provisioning of SAP Datasphere.

1. In the Resources tab, choose on the *Create*, to create a resource group for your Datasphere in your BDC.

2. In the Applications tab, choose on the *Start Provisioning* for the SAP Datasphere application. A provision wizard will appear and guide you through the provision process.

3. Once the provisioning request is created, you can explore the solution and tenant resources that were just created for the app. Information on each resource is displayed, including the allocated quota and the status. Finally, you can launch the provisioned application. <b> The provisioning of the SAP Datasphere is successful.</b> <br/>

4. In the same way SAP Analytics Cloud and SAP Databricks can also be provisioned for leveraging them in the BDC landscape.


### Provisioning of SAP Business Data Cloud Cockpit

1. To start provisioning the SAP BDC apps, you must first enable the SAP Business Data Cloud Core product. By doing so, the apps will become enabled and available for provisioning. SAP BDC Core product pertains directly to the application SAP BDC Cockpit.

<img src="images/sap4me-images/enableBdcCoreProduct.png" alt="enableBdcCoreProduct" width="1500"/><br/>

2. After adding general information, by default a new SAP BDC tenant is initiated for provisioning.

<img src="images/sap4me-images/addNewSystemAuto.png" alt="addNewSystemAuto" width="1500"/><br/>

3. Then, you provide the relevant input parameters using a guided wizard. This wizard is generated on the fly, based on configuration placed by the application owner.

<img src="images/sap4me-images/coreProductInfo.png" alt="coreProductInfo" width="1500"/><br/>
 
4. Finish the setup. <br/>
<img src="images/sap4me-images/finishProvisioning.png" alt="finishProvisioning" width="1500"/><br/>

5. When the provisioning is complete, you can explore the solution and tenant resources that were just created for the app. Information on each resource is displayed, including the allocated quota and the status. Finally, you can launch the provisioned application. <b> The provisioning of the SAP Business Data Cloud Cockpit is successful.</b><br/>

<img src="images/sap4me-images/viewResources.png" alt="viewResources" width="1500"/><br/>

6. In the **Resources** tab that opens, the application SAP BDC Cockpit displays. You can view the solution and the tenant resources that were just created for the cockpit application, including the quota and the allocated status. The status shows as **Processing** and then changes to **Ready**.
<img src="images/sap4me-images/viewResourcesCoreProduct.png" alt="viewResourcesCoreProduct" width="1500"/><br/>


7. In the **Customer Landscape** tab, you can see the provisioned tenant as an available system. Note the message that SAP Business Data Cloud Cockpit has been successfully enabled. You can launch it from **Access information** directly and log onto it. Now, you can continue with the Applications tab to continue further provisioning of other applications.

<img src="images/sap4me-images/applicationsTab.png" alt="applicationsTab" width="1500"/><br/>



### Outbound steps in S/4HANA PCE system, BTP and SCC
S/4HANA Private Cloud Edition system, which acts as a data source in SAP BDC landscape, must be prepared accordingly. All the required steps that need to be performed have been documented [here](s4-config-steps.md). There is some back and forth required between this setup and the S/4 setup, so follow the instructions accordingly.

### Creating a Formation
Formations allow you to combine SAP solution systems to simplify the connectivity setup and to provide a unified view of all components required for the implementation of your integration or enhancement scenario. Let us now look into the process of creating an SAP Business Data Cloud Formation.

1. **Customer Landscape > Systems** tab lists all the systems that are available or linked to the SAP For Me account. You can add specific systems to the Formation. To create a Formation, navigate to the **Customer Landscape > Formations** tab and select **Create Formation**.

<img src="images/sap4me-images/formationCreateStart.png" alt="formationCreateStart" width="1500"/><br/>

2. Assign a meaningful name to the Formation and select the Formation type as **Integration with SAP Business Data Cloud**. Choose Next.
<img src="images/sap4me-images/formationName.png" alt="formationName" width="1500"/><br/>

3. A specific order needs to be followed while creating the Formation. The sequence is as follows:
    - Add the newly activated SAP Business Data Cloud into the Formation first and create the Formation.
    - To the newly created Formation, add the systems in the following order:
        1. SAP Datasphere
        2. S/4HANA PCE system
        3. SAP Analytics Cloud

4. Add SAP BDC Core Tenant to the SAP BDC Formation first. Choose **Next**. After reviewing, choose **Create**. <br/>
<img src="images/sap4me-images/coreTenantInFormation.png" alt="coreTenantInFormation" width="1500"/><br/>
<img src="images/sap4me-images/bdcFormation2.png" alt="bdcFormation" width="1500"/><br/>

5. The initial Formation has been created. The other systems can be added to this SAP BDC Formation. <br/>
<img src="images/sap4me-images/initialFormationCreated.png" alt="initialFormationCreated" width="1500"/><br/>

6. Add SAP Datasphere to this existing Formation by choosing **Include Systems**. Choose **Next** and then **Include**.
<img src="images/sap4me-images/addDspToFormation.png" alt="addDspToFormation" width="1500"/><br/>
<img src="images/sap4me-images/addDspToFormation2.png" alt="addDspToFormation" width="1500"/><br/>

7. SAP Datasphere is now added to the Formation.
<img src="images/sap4me-images/dspAddedToFormation.png" alt="dspAddedToFormation" width="1500"/><br/>

8. Next, add the S/4HANA PCE system into the Formation by choosing **Include Systems**. Choose **Next Step**.<br/>
<img src="images/sap4me-images/s4PceFormationStart.png" alt="s4PceFormationStart" width="1500"/><br/>

<img src="images/sap4me-images/includeS4pceToFormation.png" alt="includeS4pceToFormation" width="1500"/><br/>

9. You are asked to input different values. Let's take a deeper look at each of the parameters required and where you can find it:
    - S/4HANA PCE Client CSR: Certificate Signing request from the S/4HANA PCE Client that was generated in this [step](s4-config-steps.md#2-generation-of-a-signed-client-certificate-csr-and-pse)
    - Instance Number: Instance Number that was recorded in this [step](s4-config-steps.md#determine-the-instance-number-for-s4-pce-system)
    - Cloud Connector LocationId: ID of the cloud connector is a optional input which needs to be provided only if there are multiple cloud connector accounts.
    - S/4HANA PCE Username and User Password: S/4HANA PCE Technical user credentials created in this [step](s4-config-steps.md#3-generation-of-the-s4-technical-user-credentials)

<img src="images/sap4me-images/s4PceDetails.png" alt="s4PceDetails" width="1500"/><br/>

10. SAP Analytics Cloud can be added to the Formation in a similar fashion as we did with SAP Datasphere.

11. Review and finish the setup. The Formation is now in **Synchronizing** state. Once the Formation is in **Ready** state, SAP Business Data Cloud tenant is ready for use.
<img src="images/sap4me-images/formationSynchronizing.png" alt="formationSynchronizing" width="1500"/><br/>


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

