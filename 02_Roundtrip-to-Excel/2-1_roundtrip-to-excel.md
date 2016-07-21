# Roundtrip To Excel

Excel and similar spreadsheet programs have always been the mainstay of data entry and analysis operations. Even with acess to more sophisticated applications, most architects and engineers, still prefer to modify parameters of projects and components with a fluid interface such as a spreadsheet so that they can take the data elsewhere and do interesting things with it.

The Revit Project being a database, always lent itself to extension using Excel. Dynamo made it even more accessible. This recipe is a small demonstration of all the pieces needed to not only extract Revit component parameters to Excel, but also push back updated data back to Revit after performing operations within Excel.

Surprisingly, the biggest challenge turned out to be not the actual connection to Excel, but the smaller nuances of how the parameter data gets modified during the process of transferring between the two applications. If you would like to skip the explanations, you can download the dataset [here](https://github.com/parametrix/dynamo-revit-recipes/tree/master/02_Roundtrip-to-Excel/datasets).

![](/02_Roundtrip-to-Excel/images/completeDefinition.png)

### Write To Excel

![](/02_Roundtrip-to-Excel/images/writeToExcel.PNG)

This step takes the existing levels from Revit and writes it into the Excel File. An important node of this definition consists of the translation of decimal feet values to fractional feet values. This easier to accomplish using Python scripts. These nodes are currently available via the Dynamo Package Manager within the 'Parametrix' package. Below are screenshots of the state of the Excel and Revit files after the first run of the definition.

![](/02_Roundtrip-to-Excel/images/excelBefore.PNG)

At the end of this step, the spreadsheet will have a all of the existing levels and their elevations from the Revit project.

### Update Excel with New Levels and Elevations

Let's say that we want to manage levels from the spreadshet. This would inlclude adding levels, removing levels, and modifying existing levels. In this example, I've modifed the levels to reflect the image below:

![](/02_Roundtrip-to-Excel/images/excelUpdated.PNG)

### Read From Excel

![](/02_Roundtrip-to-Excel/images/readFromExcel.PNG)

This part reads data from the the specified sheet. When starting off, the excel sheet is empty as it needs to be populated by information from the Revit Model. This group takes the two excel columns viz. the Level 'Name' and the Level 'Elevation' and splits them for further processing. The important thing to note here is that lengths \(Elevations\) are stored as decimal feet within Revit. This is critical is one is to perform any calulations with this information.

### Update Revit using Updated Excel Values

![](/02_Roundtrip-to-Excel/images/updateRevitFromExcel.PNG)

This group interacts with all of the other groups to update Revit and Excel with each other's values. At the end of this operation, the version held in the Excel spreadsheet will control what goes on in the Revit model.

### Create New Levels

![](/02_Roundtrip-to-Excel/images/createNewLevels.PNG)

This step will add the required levels into the Revit project should the spreadsheet require. The final state of the levels in the Revit project will be as shown in the image below:

![](/02_Roundtrip-to-Excel/images/revitAfter2ndRun.PNG)

### Video
{% youtube %}https://youtu.be/cHxfUTZtbcM{% endyoutube %}



