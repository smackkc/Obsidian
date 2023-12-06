Copies of data that can be used to restore data in a data loss event

## Rationale
Besides fans (which are fungible), storage is typically the only moving part in a system. 
Mass storage has the smallest mean time between failure (MBTF) of any system component
Data retention laws also regulate availability of certain sensitive data

## What to backup, and how
Daily backups should back up any data files that have changed throughout the day
Typically backups are taken once per day between 1 and 5 A.M., when the fewest people are using system resources
Taking backups can use a lot of system resources depending on the specifics
Becomes more complex if you need to take into account multiple time zones


## Types
Full backup - backs up the entire system every day. Called a level 0 backup in Unix systems. Easiest to restore.
Differential backups - Updates files that have been changed or added since the last FULL backup. Called level 1. Easier to restore than incremental.
Incremental - Back up files that have been changed or been added since last backup of any kind. Uses the least media, but the most difficult to restore from. Called level 2. To restore, you must first restore the last full backup, and then each increment in order.
Customizable; can be fitted to the needs of the system

By default, a system will take a full backup each time. 

A VMware Snapshot is ***NOT*** a backup because it cannot selectively restore; only the entire snapshot can be restored
## Restoration
Always begin with the last full backup
If differentials are used, need to use the latest differential next
If incrementals are used, need to restore each one in order since the full backup that was restored. 

If a mix is used, go in this order: last full, then last differential, then each incremental since the last differential in order

## Where to backup

A few options; can do a individual approach where each server has its own backup drives. The main advantage here is that it doesn't put any strain on the network, because each backup is done on the local computer. However, this can be difficult to manage at scale.

A centralized backup scales more effectively, but hits a lot of network resources. This allows many servers to backup to one centralized backup server. 

For important servers, full backups should be archived and stored offsite.
### Media
Magnetic tape is the cheapest option.
	Downsides: kinda bulky, sequential storage rather than random means it can be slower. Loses magnetism over time, so not a good archival medium.

Disk drives are the next cheapest, but more expensive than tape. They are also more reliable. They are much faster because of random access

Optical CDs are more expensive due to lower density, but last much longer. They are the ideal archival medium.

Fireproof safes are not always safe to keep media in because they keep fire out, but not heat, which can still melt the disks and the data on them.