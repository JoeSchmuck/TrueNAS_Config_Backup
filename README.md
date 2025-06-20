# TrueNAS_Config_Backup
##### Version 1.0 (20 June 2025)
---
What is this script?<br>

This is a small script to send yourself an email of your TrueNAS Configuration Files each time the script is run.<br>
This scripts works on both CORE and SCALE.

## Instructions:

1. Download the file `truenas_config_backup.txt`<br>
2. Rename the file to `truenas_config_backup.sh`<br>
3. Place this file in any directory you want, I suggest your "scripts" directory if you created one.<br>
4. Edit the script, update the three values identified above.<br>
5. Open a Shell window as `root` and run the command `./truenas_config_backup.sh` to launch the script.<br>
6. You should have an email if all goes well.<br>
7. Open the .tar file attachment and verify you can locate the two files `freenas-v1.db` and `pwenc_secret`.
8. Create a CRON Job to run this script as frequently as you desire.  This depends on how often you change your configuration.<br>
9. If you must use these files, extract them to your local computer so you can upload them using the TrueNAS GUI.<br>

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
