4pm-10pm

Fixing obsidian sync issues. Turns out the problem is line breaks, because I am running windows and windows reformats the markdown file to add an extra special character for line break(/r/n). while Linux(LF) only has one special character for line breaks(/n). In Windows(CRLF), (/r) returns the line to the beginning and (/n) moves it down to the next line in the feed. Sort of like an x-axis and y-axis. Now, how does this apply to our obsidian LiveSync? We think that every time a markdown file is opened in windows, it converts the file to CRLF and uploads that sync, hereby massively increasing the data sent and received at a much faster rate and overloading the server.

We found a .git folder in the obsidian LiveSync vault. Along with a lot of unnecessary data and plugins that we need to clean out of the database.

Discussion about blame vs. solution in an emergency situation. How blame can breed toxicity in the workplace. Instead we should work toward solutions to current existing problems to enforce holding the team together.

CouchDB design docs to ignore any syncing of 'git' files. Git files break sync. Now we have to disinfect the server and all clients that have 'git' files. Our method will be to create a new vault on the server, copy the data without git, and include a design doc that tells all syncs to ignore any files that use 'git'. Then new and previous users can sync to the new vault without uploading 'git' files. This essentially 'cures' the 'git' disease that we have allowed to infect our system.

Data Analytics Sanitize: removes and anonymize data from client PII.

Disable hidden files sync.

Backdoors:
vms in the way and we cant safeguard then
LXCs allow for pct shutdown
"pct list" shows running lxc
pct --help
pct 
"qm list" list VMs
proxmox poweroff to shutdown the server(standard linux)

creating test VM to practice VM shutdown script
Mock missions critical service VM service
First put it down properly
then test destroy it
connect to one docker node from pve shell
setup complete docker swarm shutdown
shutdown DNS last
proxy manager shutdown last
keep docker stack ON just lower the service to 0


Script1: pct inventory
pct list and awk to pull list of vms and containers(inventory)

