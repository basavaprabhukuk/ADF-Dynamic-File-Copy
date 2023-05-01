# ADF-Dynamic-File-Copy
1. The blob storage has 2 files in the Input folder.
2. Create a pipeline and use the metadata activity to create a dataset pointing to the source folder only.
3. In the FieldList, select the Child Items.
4. Use the foreach activity and select sequential in the settings.
5. In the Items setting, select the output of the Get Metadata activity, i.e. @activity('Get Metadata1').output.childItems.
6. Use the copy activity within the For each loop activity.
7. In the copy activity, create a new dataset pointing to the source folder path and create a parameter. Assign this parameter to the file name within the File path property.
8. Go back to the copy activity → Source → You will see the parameter for the file name. Select the For each loop activity output file name, i.e. @item().name.
9. In the copy activity → sink, configure the empty destination folder path.
10. Execute ADF, which will dynamically copy the file from the source to the destination ADLS2 folder.
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b9c63fa1-93d6-4e42-9590-c1d3298317df/Untitled.png)
