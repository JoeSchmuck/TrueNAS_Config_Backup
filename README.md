# TrueNAS_Config_Backup
##### Version 1.0 (20 June 2025)
---
What is this script?<br>

This is a small script to send yourself an email of your TrueNAS Configuration Files each time the script is run.<br>
This scripts works on both CORE and SCALE.

## Instructions:

Change the three variables below as desired.   
  * Email - YOU MUST DO THIS

If you would like to also maintain a copy of the config file on the server:   
   * Set TrueNASConfigBackupSave from "no" to "yes".
   * Set TrueNASConfigBackupLocation to a complete path, ex. "/mnt/mypool/backup_scripts/" or "/mnt/config_backups/".

---
## Extra Info

Run the script from CRON.  Below are possible options for user and the command line, the accounts must be setup correctly, `root` is the one that will work for certain.
* User `root`   cd /mnt/mypool/scripts && ./config_backup.sh
* User `truenas_admin`   cd /mnt/mypool/scripts && sudo ./config_backup.sh
* User `truenas_admin`   sudo ./mnt/mypool/scripts/config_backup.sh
* User `truenas_admin`   cd /mnt/mypool/scripts/ && sudo ./config_backup.sh

## Dependancies

This script utilized the `sendemail.py` script by @oxyde (on GitHub) by downloading
the python script if it does not already exist in the running directory.<br>

If this is a TrueNAS CORE system, one line will be modified to allow the use of
the `midclt` command.  This change is not required if you are using TrueNAS SCALE.<br>

You must have `root` type privledges to access the two required configuration files.
