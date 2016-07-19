# Roundtrip To Excel

Excel and similar spreadsheet programs have always been the mainstay of data entry and analysis operations. Even with acess to more sophisticated applications, most architects and engineers, still prefer to modify parameters of projects and components with a fluid interface such as a spreadsheet so that they can take the data elsewhere and do interesting things with it.

The Revit Project being a database, always lent itself to extension using Excel. Dynamo made it even more accessible. This recipe is a small demonstration of the all pieces needed to not only extract Revit component parameters to Excel, but also push back updated data back to Revit after performing operations within Excel.

Surprisingly, the biggest challenge turned out to be not the actual connection to Excel, but the smaller nuances of how the parameter data gets modified during the process of transferring between the two applications. If you would like to skip the explanations, you can download the dataset [here](https://github.com/parametrix/dynamo-revit-recipes/tree/master/02_Roundtrip-to-Excel/datasets).

