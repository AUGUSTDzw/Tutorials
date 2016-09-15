---
title: Creating a Simple OData Service
description: Creating a Simple OData Service
tags: [  tutorial>intermediate, topic>odata, products>sap-hana ]
---
## Prerequisites  
 - **Proficiency:** Intermediate
 - **Tutorials:** [SAP HANA XS Advanced, Creating a Node.js Module](http://go.sap.com/developer/tutorials/xsa-xsjs-xsodata.html)

## Next Steps
 - [Create and OData Service with Entity Relationship](http://go.sap.com/developer/tutorials/xsa-xsodata-entity.html)

## Details
### You will learn  
Create a simple OData service connecting to your table and data.

### Time to Complete
**10 Min**.

---

1. Right mouse click on the `js/lib/xsodata` folder and choose `New->File`. 

	![New file](1.png)
	
2. Enter the name as `businessPartners.xsodata` and click "OK".

	![file name](2.png)

3. You want to define an OData service to expose the business partner table. The syntax of the XSODATA service is relative easy for this use case. You need only define a namespace (your package path), the name of the HANA Table you will base the service from (`dev602.data::MD.BusinessPartner`) and the name of the OData entity (`BusinessPartners`). Therefore the content of the XSODATA file would be. Note: if you don’t want to type this code, we recommend that you cut and paste it from this web address `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex3_10`
	
	![odata service](3.png)
	
4. Save the file. Run the Node.js module. You will receive the unauthorized message as expected. Then run the `html5` module (defined as `web` earlier). Change the URL path to `/xsodata/businessPartners.xsodata` to test this new service. The resulting document describes the service entities.  You have the one entity named `BusinessPartners`. 

	![save file](4.png)

5. You can now adjust the URL slightly and add the `/$metadata` parameter to the end of it. 
	
	For Example: `/xsodata/businessPartners.xsodata/$metadata`
	
	You can see the field descriptions for all the attributes of the OData service.

	![access metadata](5.png)
	
6. In order to view the data of the entity, you would append `BusinessPartners` to the end of the URL:

	![output](7.png) 

## Next Steps
 - [Create and OData Service with Entity Relationship](http://go.sap.com/developer/tutorials/xsa-xsodata-entity.html)