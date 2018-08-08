# FOLIO-backup-and-restore
## Current functionality:
* Backs up and restores data from a FOLIO tenant after reset. What data that gets reset depends on configuration.
* Populates a permission set with every single permission there is. Usable for when you want to configure Admin rights to a FOLIO user without letting them be the Admin itself

## Caveats 
Not all data and all API:s are suitable for this script. The aim if mainly for parameter settings, and not the module's data. Please report anything you find that is not compatible. 
As of now, the following things are not restoreable:
* Permissions

## Requirements
Python 3. 
[Download instructions](https://www.python.org/downloads/)

## Usage
### Populate permissions
* Create a permission set in FOLIO through the UI, Copy the ID.
* run the following command:    
`python3 populatepermissions.py [okapi_url] [tenant_id] [x-okapi-token] [permission_set_id]`

### Backup
* Note what data you want to backup (and restore)
* Make a copy of the settings.json.template file and rename it settings.json
* Using the API reference (link below), populate the settings.json with the parameter settings you like to backup. 
* run the following command:
`python3 backup_and_restore.py backup [path_to_store_date] [okapi_url] [tenant_id] [x-okapi-token] [permission_set_id]`

### Restore
Given you have backed up your data according to the above guide. Run the following command:
`python3 backup_and_restore.py restore [path_to_store_date] [okapi_url] [tenant_id] [x-okapi-token] [permission_set_id]`

## Reference
[FOLIO API reference](https://dev.folio.org/reference/api/)
