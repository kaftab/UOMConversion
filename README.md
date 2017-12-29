# UOMConversion
The project allows adding locale based standard units to properties of any ItemType. Property values are converted to be displayed in the units of the browser locale. A sample application to the Part ItemType is included in the package

# Steps for Configuration (A sample configuration is included in the package)
1. Modify the itemtype that has the properties  
1.1. Add dimensional property(s) to the itemtype and form  
1.2. Add a UOM property to the itemtype and form, set a default value (used when locale is not defined)  
1.3. Make the UOM property “Disabled” on the form   
1.4. Ensure UOM property “Name” is same as the Data Source name   


![image](https://user-images.githubusercontent.com/27519066/34441475-01487b58-ec8a-11e7-8846-ae1bb93707d1.png)

![image](https://user-images.githubusercontent.com/27519066/34441074-756e8250-ec87-11e7-9ef9-27212340e914.png)

![image](https://user-images.githubusercontent.com/27519066/34441526-4a206912-ec8a-11e7-99f5-ae016aefd5c0.png)

2. Add method “UOM_OnFormPopulated” to the form “onFormPopulated” event

![image](https://user-images.githubusercontent.com/27519066/34441111-abd130b8-ec87-11e7-8b3a-18fafbaf3723.png)

3. Ensure that the List "UOM" has all the units you want to use

![image](https://user-images.githubusercontent.com/27519066/34441153-e6ecae98-ec87-11e7-8f78-fd360bd39c17.png)

4. Ensure that the List "UOM Multipliers" has all the conversions for the units you want to use

![image](https://user-images.githubusercontent.com/27519066/34441184-0a1b752a-ec88-11e7-8c21-dce6168eb6ae.png)

5. Create a new UnitConversion item
5.1 Administration --> Unit Conversion --> File --> New
5.1. Select the itemtype that this applies to
5.2. Select the UOM property this applies to
5.3. On “Locale Units”, define a standard unit for each locale
5.4 On “Associated Properties”, add properties associated with this UOM

![image](https://user-images.githubusercontent.com/27519066/34441228-558e2232-ec88-11e7-8915-87f96518bd50.png)
