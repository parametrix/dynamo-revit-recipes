# Update Tag Parameters

![](/03_Place-and-Update-Annotation-Tags/images/3-2_UpdateTags_Overall.png)

This example of updating Generic Annotation Tags using the Area objects is pretty similistic. This will need to be modified if the Tags were not placed by the Dynamo Graph \(for example, consider the scenario where the user manually decides to place Tags intending the Dynamo Graph to update it\). In other words, Dynamo know how to connect the Tags to the areas based on the sequence they were placed. If this sequence were to be broken, then the graph needs to be modified such that Dynamo correlates at least one property of the tag \(such as the apartment name\) and then matches the other parameters \(areas in this case\) and then updates them.

### Video
{% youtube %}https://youtu.be/mrYsacpRpGM{% endyoutube %}


