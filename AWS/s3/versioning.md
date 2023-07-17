If versioning is disabled any file in a bucket has null ID.
That means, when versioning is enable, the files can have the same name and **different IDs**. The files with the same name and different ids will be retained on a bucket. 

Specifing ID can give us access to specific version of a object on a bucket. Without specifing, the newest version of a file is returned. 

Deletion of files is applied by **Delete Marker**.
Delete marker will hide old versions of specific file in the bucket. It will not explictly delete them . The applience of delete marker can be reversed!

For real deletion **Version delete** should be applied. Without specifying the ID, the newest version of a file will be permanently deleted. 

----------
Object versioning CANNOT be switch off. 
