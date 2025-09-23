[[WorkAdventure Map Project Outline]]


Infrastructure
-LXC of Ubuntu or Docker
	-Create a stack file
		-Remove the need for TRAEFIK
	-Create self-hosted authentication server
	-Create Github repo for Infrastructure
	-Create Github Repo for map-storage

Create map host server with Github pages

Useful links:
[workadventure github](https://github.com/workadventure/workadventure)
	[mapbuilding docs](https://docs.workadventu.re/map-building/)
	[TILED docs](https://docs.workadventu.re/map-building/tiled-editor/)

[Self Hosted Infrastructure Guide](https://github.com/workadventure/workadventure/blob/develop/docs/others/self-hosting/install.md)

[My Github Repository](https://github.com/rigunkes/workadventure)


You will need to create a server for hosting WorkAdventure itself. I used docker to build the workadventure server. Here is a link on [Self Hosting WorkAdventure with Docker Compose](https://github.com/workadventure/workadventure/blob/develop/contrib/docker/README.md).

The Bellingham Makerspace Infrastructure uses a Virtualization Host Operating System called Proxmox. In Proxmox you can use community scripts called LXC's to make containers of various operating systems and applications. I will use a docker LXC community script to quickly boot up a container of docker that will be running containers of workadventure! Container-ception! This allows for the system to allocate the bare-minimum resources while allowing for scalability and a smooth running operation.

I have my own [Github Repository](https://github.com/rigunkes/workadventure) that holds all the files for our custom maps, assets, and infrastructure files(stack and compose files for docker).

Default Compose File:
[docker-compose.prod.yaml](https://github.com/workadventure/workadventure/blob/develop/contrib/docker/docker-compose.prod.yaml)

-compose files
-how to use NGINX instead of TRAEFIK
-

To self-host a functioning WorkAdventure server, you need an authentication server for managing users and roles. Here is a link to my journey on building a [[Authentication]] server.

You will also need to build a map or choose a existing map from the internet. Here is a link to my journey on [[TILED Map Building]]. Here is a link to [WorkAdventure Community Assets](https://github.com/workadventure/awesome-workadventure). 

Need to change SECRET_KEY in .env to protect encrypted data in workadventure

