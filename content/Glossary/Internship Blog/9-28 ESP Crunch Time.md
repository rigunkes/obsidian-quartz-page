2pm-

High Priority Goals:
Three scripts
 - Server hardware shutdown
 - Docker node shutdown
 - Virtual ware shutdown

Medium priority
 - Discuss cybersecurity comp structure and plans

Low Priority
 - Plan IT layout and closet setup
 - Plan prod server install

Standup
	What you accomplish
	What you're doing
	What are your roadblocks

Daily plugin and tasks plugin and cardboard/kanban
Future:
	Mac addresses


 
Note:
	In future add the discovery as a 'folder note'
	NFS pool is on pve(cant move LVM shares)
	Need to setup NFS share with three nodes at two locations
	less RAM and CPU but fast SFP ports for quick data transfer
	ZFS? copy on write
	timed iterative backups


RSYNC
cheap and quick backup solutio
ai helps with options

cp doesn't copy permissions, ownership, flags, links
how to keep details of files?

rsync -via --progress [\source\] [\target\]
a=archive
	rlptgoD
v-verbose
i=itemize changes
	change summary for updates
	extra verbose
--progress
	adds progress bar visual

file sys to file sys
can do remote with encryption
secure offsite backup solution
can do iterative backups
cp -r works
rsync

linux object oriented

rsync -via --progress A/ B/
creates B
slash adds object to tell the 'contents' to be copied(treat the directory as a root)

rm -rf B/*
to delete contents

rm -rf A
deletes EVERYTHING

if cancelled backup in the middle it does not restart
it will resume and skip the already backed up files


NFS
should have an admin root  account with only 3ppl having access
root is the only account has access to every file

turtles all the way down

reserve IP in dhcp for backdoor
ALWAYS DOCUMENT BACKDOORS
CC someone outside of group that you trust
get witness if find someone breaks rules and adds backdoors
print out evidence
MAC address
100% honest with boss and skip



/etc/nfs.conf
exports
rootdir=
cat /etc/exports
pulls IP from DHCP

with a reserved DHCP it is less obvious to leave access
add the reserved address to the nfs /etc/exports config

NFS needs to have 'trusted' IPs in the exports file to be able to mount files externally

sudo mount 10.10.0.24:/nfs/pools/pool1 /mnt/bms_nfs

mkdir in /mnt/
sudo mount ip

sshdconfig

rsync -via --progress --exclude 'filepath' username@ipaddress

root is the same on every machine

'mc' tool file explorer

git clone = you own all the files
quartz problem
meld <onedirectory> <anotherdirectory>


created git repository for hybrid-remote code working