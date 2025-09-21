# (Intermediate) Inventory Data Analysis
### An intermediate data inventory analysis project based on SAP public data.



###### *Data provided by SAP S/4HANA Cloud Public Edition in a free trial.*



### Synopsis:

  Run a basic inventory analysis for a fictional bicycle company (Velotics Inc.) using SAP to run inventory
  and form a Data Analysis to present for upper management (i.e. the company buyer and CEO). This analysis
  will convey fullly completed product inventory in the following order;
  - Data Sources
  - tools
  - Enterprise Explanation
  - Data Procurement
  - Reporting
  - Data Visualization & Dashboard
  - Presentation & Analysis



### Data Sources:
The primary data source is SAP S/4HANA Cloud Public Edition 14-Day Free Trial which is accessible via
website link: https://www.sap.com/products/erp/s4hana/trial.html


### Tools
- SAP S/4HANA Cloud (Public Edition) - Data Procurement
- Microsoft Excel - Data Conversion & Data cleaning
- SAP S/4HANA Cloud -  Reporing
- Microsoft Excel - Reporting
- Tableau - Data Visualization & Dashboard
- Mac Keynote - Presentation
- Microsoft Excel - Final Presentaion & Analysis



### Enterprise Concept:

  <img width="814" height="407" alt="Velotics Inc  Busines Entitiy Visual" src="https://github.com/user-attachments/assets/15c119ee-dc42-4d3b-9931-4df7e0ba6c46" />

  The illustation above provides the enterprise concept as it exists in a fictional entity. Velotics Inc. utilizes a ERP (Enterprise
Respurce Planning) system, which in this case uses SAP to organize the businesses functions. We will use this ERP to produce an
inventory report and analysis to help the company buyer know what inventory levels are. Therfore, the inventory report will guide 
the buyer and other related upper managment to better strategize product inventory and or sales targets.


Velotics Inc. produces bikes in the follwowing lines/ ranges:
<img width="782" height="456" alt="Products" src="https://github.com/user-attachments/assets/56297518-d148-46cc-bd87-dab71b0e18ec" />


 *As pictured, Velotics produces racing bikes, mountain bikes, cruise bikes, youth bikes, e-bikes and an in home exercise bike.
 All of these bikes have corresponding model numbers and encomapss ranges in competitive bicycle market segmets*


*Disclaimer: For this inventory analysis, I will only cover "Fully produced product" as each product model
 contains numerous parts and componemts that they themselves have stock/ part #'s to categorize
 e.g. see the model part example as shown in the depiction below*
 

<img width="782" height="456" alt="Parts:Components per model" src="https://github.com/user-attachments/assets/30f7bf06-dd98-4c69-8b42-7544b5dd5931" />








### Data Procurement:

To find, collect and consilidate all the KPI's needed for the inventory report. I first access SAP using my credentials to run
a live inventory based on single material (i.e. finished product) stock. the following SAP hompage is shown :


<img width="1296" height="842" alt="SAP Velotics Hompage" src="https://github.com/user-attachments/assets/3aee8840-710f-4eb1-bc6b-e224e16d1d75" />

Next, I navigate the homepage to Manufacturing & Supply Chain to access the correct fiori Launchpad. The navigation to run inventory
is as follows:
  `Manufacturing & Supply Chain > Warehouse Management > Stock *Sinlge Material*`
  

<img width="1296" height="827" alt="fiori_launchpad" src="https://github.com/user-attachments/assets/b0aa1e0b-6cff-4c52-9d13-cbe18445dada" />




Subsequently, I then query each finished product model by manually entering each one since the SAP s/4HANA
free trial version does now allow you to download the inventory into a file to start the spreadsheet
development. Normally I would download or run ERP runctions to obtain the finished product model's 
inventory in one single action, but for all intensive purposes I manually queried each into the 
fiori launchpad function (Single Stock Material).
  

<img width="1362" height="651" alt="ERP Single stock query" src="https://github.com/user-attachments/assets/03bf4b19-5a6b-4146-be5f-3bba4dd0b431" />



Lastly, I ran a final stock search to proivde final details about each model's stock by the following navigation:
`Manufacturing & Supply chain > Warehouse Management > Manage Stock`

<img width="1296" height="540" alt="Stock Management query" src="https://github.com/user-attachments/assets/c52376aa-008c-46b5-ac4d-d3723520f2a5" />














