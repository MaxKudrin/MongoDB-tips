# MongoDB tips

## List
1. Add user in mongo Shell  
2. Import data from "`bson`" format, `mongorestore`


### 1. Add user in mongo Shell  
`use dbName` - switch to DB   
`db` - to show current DB  
`show users` - shows list of DB users

```
db.createUser({
user : "Max",
pwd : "12345",
roles : ["readWrite","dbAdmin"]
});
```
### 2. Import data from "`bson`" format, `mongorestore`

 You need to download devtools from mongo page, then copy tools to bin folder. </br>
<span style="color: orange; font-weight: bold">
For importing the .bson file in MongoDB, just type the following onto the CMD (not mongo shell):
</span>
```
mongorestore -d db_name -c collection_name /path/file.bson
```
If there is only a single collection then refer the following code:
```
mongorestore --drop -d db_name -c collection_name /path/file.bson
```
And regarding the restoring procedure for the whole folder that is being exported by mongodump, refer the following code:
```
mongorestore -d db_name C:\anyDBfolder\
```