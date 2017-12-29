# UOMConversion
The project allows adding locale based standard units to properties of any ItemType. Property values are converted to be displayed in the units of the browser locale. A sample application to the Part ItemType is included in the package

## Part in US Locale:  

![image](https://user-images.githubusercontent.com/27519066/34441904-a8762b80-ec8c-11e7-9e30-f1c5c73161d6.png)

## Same Part in French Locale:  

![image](https://user-images.githubusercontent.com/27519066/34441887-9460530a-ec8c-11e7-95e0-01db4be76666.png)





## Project Details

**Built Using:** Aras 11.0 SP11

**Browsers Tested:** Internet Explorer 11, Chrome

> Though built and tested using Aras 11.0 SP11, this project should function in older releases of Aras 11.0 and Aras 10.0.

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
    * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
    * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\UOMConversion\Import\imports.mf` file in the Manifest File field.
6. Select **Select All Packages** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool. 
















# Steps for Configuration (A sample configuration is included in the package)
## Modify the itemtype that has the properties  
1. Add dimensional property(s) to the itemtype and form  
2. Add a UOM property to the itemtype and form, set a default value (used when locale is not defined)  
3. Make the UOM property “Disabled” on the form   
4. Ensure UOM property “Name” is same as the Data Source name   


![image](https://user-images.githubusercontent.com/27519066/34441475-01487b58-ec8a-11e7-8846-ae1bb93707d1.png)

![image](https://user-images.githubusercontent.com/27519066/34441074-756e8250-ec87-11e7-9ef9-27212340e914.png)

![image](https://user-images.githubusercontent.com/27519066/34441526-4a206912-ec8a-11e7-99f5-ae016aefd5c0.png)

## Add method “UOM_OnFormPopulated” to the form “onFormPopulated” event

![image](https://user-images.githubusercontent.com/27519066/34441111-abd130b8-ec87-11e7-8b3a-18fafbaf3723.png)

## Ensure that the List "UOM" has all the units you want to use

![image](https://user-images.githubusercontent.com/27519066/34441153-e6ecae98-ec87-11e7-8f78-fd360bd39c17.png)

## Ensure that the List "UOM Multipliers" has all the conversions for the units you want to use

![image](https://user-images.githubusercontent.com/27519066/34441184-0a1b752a-ec88-11e7-8c21-dce6168eb6ae.png)

## Create a new UnitConversion item  
1. Administration --> Unit Conversion --> File --> New  
2. Select the itemtype that this applies to  
3. Select the UOM property this applies to  
4. On “Locale Units”, define a standard unit for each locale  
5. On “Associated Properties”, add properties associated with this UOM  

![image](https://user-images.githubusercontent.com/27519066/34441228-558e2232-ec88-11e7-8915-87f96518bd50.png)

![image](https://user-images.githubusercontent.com/27519066/34441593-c19faebc-ec8a-11e7-98c0-e6e42a96cae9.png)

![image](https://user-images.githubusercontent.com/27519066/34441602-d638fb58-ec8a-11e7-87c0-560bf1376ecf.png)

