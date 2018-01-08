# postgresql-gce-backup
Backup solution for Google cloud backup of postgreSQL

Docker image that allow postGreSQL backup base on the configuration:

- Connection informations
PG_HOST= "xx.xx.xx.xx"     
PG_PORT=5432       
PG_USER="postgres"      
PG_PASSWORD="password"      
PG_DBNAME="dbName"

- Google cloud destination for backup files  
BACKUP_DEST="gs://my-bucket"   
BACKUP_FOLDER="dbName"

- Backup retention time in days, the script must remove the olders backups  
BACKUP_RETENTION_DAYS=7     

- Run backup based on this cron  
BACKUP_CRON_EXPR="* 1 * * *"   

- Send email on backup error with the error message and stacktrace inside the log    
EMAIL_TO_NOTIFY_ON_ERROR ="error@gmail.com"   

- Send email on backup success with the link to the gce bucket backup file and the size of the file  
EMAIL_TO_NOTIFY_ON_SUCCESS  ="success@gmail.com"  
      
Will send compressed backups to Google cloud bucket

## Delivrables:

- Docker image  
      1) Fill the Docker file with the postgresql backup image creation   
      2) Fill the script folder by our script  
      3) Complete the ci-postgres-backup-pod.yaml with the kubernetess pod definition  
- Kubernates yaml file
- Tests
- Recovery script, how to restore a specific backup file

## Conditions:

- Bug support: 2 months
- You will be payed when tests will be ok on my project
