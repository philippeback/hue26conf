# Get Hue 2.6 to work on Hortonworks Sandbox 2.4

It is a pain to get working, I suppose that this is due to Hortonworks going all in on Ambari Views.

Still. A pain.

## Update configuration of Hue

Change the file in `/etc/hue/conf/hue.ini` to the one provided.

It does the following: let people login without any password.

It avoid the Django yellow screen.

Also, the hue config contains `localhost` for some elements (WebHDFS) where it should be using `sandbox`.

## Start the Hue service

Ssh into the box (default password is `hadoop`.

	ssh root@sandbox

Start the service

	service hue start

If you want this to persist between reboots of the SandboxVM

	chkconfig hue on

## Access Hue

	http://<ip>:8000

Hue user: hue
Hue password: 1111


