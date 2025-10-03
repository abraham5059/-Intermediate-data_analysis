# (Intermediate) Inventory Data Analysis
### An intermediate data inventory analysis project based on SAP public data.



###### *Data provided by SAP S/4HANA Cloud Public Edition in a free trial.*



### Synopsis:

  Run a basic inventory analysis for a fictional bicycle company (Velotics Inc.) using SAP to run inventory
  and form a Data Analysis to present for upper management (i.e. the company buyer and CEO). This analysis
  will convey fullly completed product inventory in the following order;
  - Data Sources
  - Tools
  - Enterprise Explanation
  - Data Procurement
  - Data Reporting
  - Data Visualization & Dashboard
  - Presentation & Analysis



### Data Sources:
The primary data source is SAP S/4HANA Cloud Public Edition 14-Day Free Trial which is accessible via
website link: https://www.sap.com/products/erp/s4hana/trial.html


### Tools
- SAP S/4HANA Cloud (Public Edition) - Data Procurement
- Microsoft Excel - Data Conversion & Data cleaning
- SAP S/4HANA Cloud -  Reporting
- Microsoft Excel - Reporting
- Microsoft Power BI- Data Visualization & Dashboard
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



### Data Reporting:




<img width="1248" height="748" alt="Inventory Daily Report V1" src="https://github.com/user-attachments/assets/78d96efd-dbef-44ff-a13a-19cca2472d7e" />


To continue on with the next phase of the inventory analysis, the development of a daily inventory report was created to distribute
daily inventory report about completed product in stock for upper managment to assess.


<img width="1436" height="814" alt="daily inventory report" src="https://github.com/user-attachments/assets/57271044-f09c-46a1-9e71-eabd1ff397b7" />

This report feautures quick Microsoft Excel formulations to easliy report inventory. such as:

- Availible Unrestricted total: `=SUM(F36-G36-H36-J36)` *for the total sellable stock in inventory*
- Pending Stock total: `=SUM(G36+H36+J36)`   *includes quality inspection, retunrs and blocked stock (uncertainty of stock)*
- Average Coverage of Days: `=AVERAGE(P6:P34)`   *gives the total average rate of 30 day product consumption based on current movement on all items*
  

Product model is replicated if there are multiple storage locations associated with current inventory. Therefore there are multiple
of the same product models to further detail where exacly that inventory is at what stage of stock. For example:

  *MZ-FG-M525 (Mid-Range mountain bike) has 5 different stock locations: 227 peices are under QI, 3,835 are in std. storage 1
    while 99 peices are stored in the warehouse. there are no peices that are blocked.*

<img width="1366" height="273" alt="Screen Shot 2025-09-22 at 11 42 41" src="https://github.com/user-attachments/assets/7b4d2ed2-420b-4486-824e-43a862bdb78f" />

*this example inventory report can be executed in the SAP fiori lauchpad query by:
   `Manufacturing & Supply Chain > Warehouse Management > Stock *Sinlge Material* > Material > (type the model numer).`
   
<img width="1134" height="711" alt="Screen Shot 2025-09-22 at 11 43 05" src="https://github.com/user-attachments/assets/755fe194-44e8-4a6a-8929-74ca8f542ff1" />



Lastly, this report also features what exacly needs to be orderd/considered given pruchasing material for finished product.
Such as formulating an if statement before each product model :
  `=IF(AND(F6<=0, E6="Std. storage 1 171A",P6>0), "Yes", "No")` 


The condition is as follows:
- `...f6<=0, ...` Unrestricted-Use Stock is less than or equal to 0
- `... E6="Std. storage 1 171A", ...` only for stock in storage 171A is used
- `...P6>0 ...` the 30-Day supply coverage needs to be greater than 0. optimized for stocking moving product



<img width="1134" height="558" alt="Order conditional result" src="https://github.com/user-attachments/assets/3497f3b8-5f1a-43df-952e-4cd51f68c7c9" />


*therfore, after applying the formula parameters to determine which finished product needs order prioriry to balance product movement.*
*Here, the result is model MZ-FG-26EMN (Mountain E-Bike) with 0 Unrestricted stock at a 3.57 consumption rate. Therefore, the finished
product needs order raw material consideration in order to meet supply, which can affect sales and procurement*






### Data Visualization & Dashbord:



SAP does provide built-in interative dashboards and data visualization as part of an ERP system.

In this case, to view  the SAP automated overall inventory dashboard, navigate by the following:
`Manufacturing & Supply Chain > Warehouse Management > Overview Stock Management > Plant (Select "Plant 1 US (1710)" > Go`

*which produces the following interactive live dashboard*


<img width="1334" height="837" alt="Screen Shot 2025-09-22 at 11 14 10" src="https://github.com/user-attachments/assets/d083148f-e66d-4ce9-8b05-52d6f4e6d3fd" />


We can interact with areas on concern for Velotics such as Overdue Materials tile:


<img width="388" height="794" alt="Screen Shot 2025-09-22 at 11 14 31" src="https://github.com/user-attachments/assets/551f0079-e5f5-41b1-83e9-713658f98dc1" />

Which if we click on it; we can see in futher detail what the overdue material is to account for current inventory stock.


<img width="1366" height="441" alt="Screen Shot 2025-09-22 at 11 14 51" src="https://github.com/user-attachments/assets/ec14acee-82e3-4c82-a158-5d9dea3415e0" />

*Here, we can see the only item that the ERP system is accounting for. 2 pruchase orders of a forklift with a window of a 7 day transit
  period. (which may be accounted for the plant 1 US 171's inventory count once the forklifts arrive)*
  


Other visual graphics that can be used for the inventory analysis would be to create pivot tables and or data visualizations within the 
daily FERT inventory report. That way when the report is sent to upper management, they can visually assess the inventory for the day and make
key decisions to help with product movement.



<img width="1084" height="828" alt="Pivot Tables and Pie Chart Vizuals in Report" src="https://github.com/user-attachments/assets/1aedee9d-75d3-470d-8d16-0b92790cd5e1" />


*Here, I have developed key visuals within the report by the use of pivot tables and a pie chart that (like a basic report specific 
dashboard) help managment make quick and easy daily decisions when viewing the inventory report in the same workbook.*

Next, the use of the pivot tables and data visualization within the data inventory report can be used towards the data presentation.



After completing the Microsoft Excel visuals, I then proceed towards creating a Microsoft Power BI Dashboard/ Visualizations.

- 1st. when launching Power BI, the starting menu asks for a data source to build and create the dashboard.
- 2nd. load the data into the data source reciprocal in Power BI *(in this particular case, I had to use the online paid platform since
        I don't have business or university credentials to use the app freely. Threfore, OneDrive and other Microsoft 365 services were
        out of my reach. I had to copy/paste the Veltoics FERT Daily Inventory spreadsheet to start the Power BI Data Visualization session.)*
<img width="1503" height="611" alt="inital loading screen" src="https://github.com/user-attachments/assets/a8276eb4-90c5-4e4c-9254-c43d25b76fd8" />

  
- 3rd. ensure the data looks good and clened to base analytics for the dashboard. See image below:
<img width="1047" height="758" alt="Data loading in Power BI" src="https://github.com/user-attachments/assets/48ff4382-b4e0-4577-a9b4-28c9177e68d9" />



- 4th. Auto-Create the interactive dashboard once the spreadsheet is loaded into Power BI and begin to Visualize.

  
<img width="1624" height="801" alt="inital Summary" src="https://github.com/user-attachments/assets/4258fdd4-2c1a-4620-b926-97fecd42d797" />


Once the interactive dashboard workspace has been created, I then apply subsequent filters within the dasboard to produce meaningful 
visualizations. The purpose of using Power BI after Excel is to futher enchance the data and apply interactive visualizations for upper
managment, staff and inventory stakeholders to explore the Velotics day inventory at depth. 

*For example, we can see total coverage of days by product model when applying the data filters of Plant, Product Model & Blocked Stock*

<img width="1501" height="705" alt="Summary Overview Filtering" src="https://github.com/user-attachments/assets/92a090eb-e92e-4b0e-b28f-d2aa73c00672" />

*here we can see that MZ-FG-EBO1 (Standard E-Bike) , MZ-FG-M525 (Mid-Range Mountain Bike), & MZ-FG-26XR1 (In-Home Exercise Bike) account 
for the majorty of 30-day stock coverage. Anything below 5 days would be highly considered to increase stock of finsihed product in 
respect to keeping inventory levels constant without over producing stock that doesn't sell in high volumes.* 


*Another example would be to see all total stock of locations other than the most popular location i.e. Std. Storage 1 171A*
*Simply click + adjust the nessesary parameters within the data visualization while also allowing highlighted views*

<img width="931" height="491" alt="interacting with dashboard" src="https://github.com/user-attachments/assets/819edfdb-b432-4b39-b088-a5fbd4b1d520" />

Lastly, the dashboard is created and will be shared within Veltoics Inc. to related memebers of the inventory analysis via Mikcrosoft 
Outlook Mail/Teams. 

<img width="1449" height="794" alt="Screen Shot 2025-10-03 at 14 45 25" src="https://github.com/user-attachments/assets/22d940e7-abaf-4f31-ad9c-c67674abad37" />




### Final Presentation & Analysis : 

To continue on with the last part of the iventory analysis process, a presentation about the data findings will be created by
Microsoft PowerPoint.




  
