# ADF-Dynamic-File-Copy
Dynamically read file names and copies it to other folder
# Azure-Dynamically read file names and copies to other folder

1. The blob storage has 3 files, in the folder Input.
2. Create the pipeline and use the metadata activity and configure the sorce folder upto to the Input blob storage and select the childNames; In the [childName.name](http://childName.name) we can find the name of the filename
3. Use the foreach activity and assign the output of metadata activity Output.childname and use the sequential.
4. within copy activity use the copy activity, in the source → configure the linked service and for the dataset filename do not assign any value as these needs to get the value from for each loop activity dynamically; so create the parameter and assign the paramter to file name property to source. And this paramter will get the value from foreach loop variable  output.childname.name
