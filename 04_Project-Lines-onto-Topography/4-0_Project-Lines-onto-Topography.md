# Project Lines onto Topography

Projecting Lines onto Surfaces within Revit has been tricky for various reasons. One could argue that projecting lines  and modeling with primitives are precisely the kind of things Revit was designed to avoid; and I agree with this attitude. But, there are times when you simply want something done a particular way. Fortunately Dynamo can let you be that impish individual that you want to be within the Revit world.

![](/04_Project-Lines-onto-Topography/images/4-0_projectedline.PNG)

### Dyanamo and Adaptive Lines

This recipe documents the process of using Dynamo to project Property Line elements on to the Toposurface within the Revit Project. The actual line work is somewhat tricky. One cannot use Revit's Model Lines for this purpose because each _Model Line_ needs to be associated with a _Sketch Plane_. With a Complex Toposurface, this approach can be extremely convoluted. A simpler approach is to use a linear element that is not tied to a Sketch Plane. The only class of elements within Revit that allows non-associative placement is the _Adaptive Component Family. Accordingly, the projection lines are traced at the start point and end points using a single Adaptive Component consisting of two \_Adaptive Points_ and a Model Line stretching between them. The complete graph and family can be found [here](https://github.com/parametrix/dynamo-revit-recipes/tree/master/04_Project-Lines-onto-Topography/datasets):

![](/04_Project-Lines-onto-Topography/images/4-0_Overall.png)

### The Uncomplicated Approach

One can of course eschew the complicated approach of using Dynamo and simply use the Sub Region within the Massing and Site toolset. The results are acceptable except for the fact that one cannot change the Line Style or host any other family along the line. The image below shows the results of using the Sub Region.

![](/04_Project-Lines-onto-Topography/images/4-0_Sub-Region.PNG)

