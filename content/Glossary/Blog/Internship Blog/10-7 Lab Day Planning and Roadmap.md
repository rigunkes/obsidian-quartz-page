3pm-9pm
Started creating a plan for network templates. Talked with Vivi & Lili about what we should start with, who should work on which segment and what is required for each segment while documenting each part.

Brian showed up and I switched gears into showing him around our network and talking about Cascade STEAM's goals and projects.

Worked Some more on Network Templates until Garth showed up. Then we work on setting up a curl link for the GitHub journal presentation. He shows me a couple of ideas and I get to discovery. 

I spend some time researching and trying a couple of different solutions.

One solution I thought of was to upload the workflows file to GitHub, then curl the raw file data link and then output the raw file data into a new file on the target's local machine. I then decided that the raw file data link was too long to type out for the presentation, so I wanted to create a proxy for 'raspberrypiclub.org/blogging/deploy.yml' but no matter what I tried the link would never resolve to the raw data file. So I opted for a slightly simpler solution. 

I proxied the previous link to go to the GitHub page for the 'deploy.yml' file and then instruct the target to click on the RAW file link and then copy that link from the address bar and curl it in their terminal.

I added this solution to the slideshow and moved on to something new.

While switching gears we encountered an issue in our obsidian livesync database. Lili joined from her remote desktop. Then suddenly, there were missing documents from our database. After a moment of panic we found out that there is a file recovery tool built into obsidian. We recovered the files from our local backups.

Then we proceeded to edit our user account permissions for the CouchDB server hosting the databases. We try to edit my account to be a user and not an admin. However we were having authentication issues because the livesync server was constantly authenticating with the old incorrect password.