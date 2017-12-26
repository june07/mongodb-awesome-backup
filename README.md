What is mongodb-awesome-backup?
-------------------------------

mongodb-awesome-backup is the collection of scripts which backup MongoDB databases to Amazon S3.


Requirements
------------

* Amazon IAM Access Key ID/Secret Access Key
  * which must have the access lights of the target Amazon S3 bucket.

Usage
-----

```bash
docker run --rm \
  -e AWS_ACCESS_KEY_ID=<Your IAM Access Key ID> \
  -e AWS_SECRET_ACCESS_KEY=<Your IAM Secret Access Key> \
  -e S3_TARGET_BUCKET_URL=<Target S3 Bucket URL (s3://...)> \
  [ -e BACKUP_FILE_PREFIX=<Prefix of Backup Filename (default: "backup") \ ]
  [ -e BACKUPEDDAY=<Day which file is backuped specified in format yyyymmdd (default: <TODAY>) \ ]
  [ -e MONGODB_HOST=<Target MongoDB Host (default: "mongo")> \ ]
  [ -e MONGODB_DBNAME=<Target DB name> \ ]
  [ -e MONGODB_USERNAME=<DB login username> \ ]
  [ -e MONGODB_PASSWORD=<DB login password> \ ]
  [ -e MONGODB_AUTHDB=<Authentication DB name> \ ] 
  weseek/mongodb-awesome-backup
```

and after running this, `backup-YYYYMMdd.tar.bz2` will be placed on Target S3 Bucket.
