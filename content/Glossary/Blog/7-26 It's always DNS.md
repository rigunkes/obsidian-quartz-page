showed up at 4pm, Garth immediately left.

I work on my GitHub page for about 30 minutes.

Eventually, I try to solve the 'workadventure' address resolution issue.

I mess around in NGINX and Technitium for about an hour until I switch everything to HTTPS instead of HTTP.

I gave it an SSL certificate and changed the forward port to 443.

The address is now able to resolve.

However, the audio and video stream does not work.

I tried to create a 'Stream' entry in NGINX but that did not fix the issue.
(I may need to adjust the incoming ports and/or some other settings in the entry.)

Then the 'bellinghammakerspace.org' and 'members.bellinghammakerspace.org' domains stopped resolving.

I gave Garth a phone call and shared my screen on discord while we troubleshooted the issue.

members... was fixed quickly by simply adding a CNAME record into Technitium.

However, for 'bellinghammakerspace.org' we needed to add a www A record for the website public IP and a root(@) domain CNAME record that points to www
(may need to swap these in the future but it works now.)
