---
layout: post
title: Setting up openVPN in the cloud (AWS)
---

We are going to setup a vpn server in the cloud on AWS for free! I repeat for free!.

You will need a free AWS account if you dont have one [signup](https://www.youtube.com/watch?v=bgPuPSPZe2U).

First thing is to open up your web browser and navigate to [aws.amazon.com](https://aws.amazon.com/) to login to you aws console.

Once your all set and logged in, we start setting up the vpn.

## Setup an instance that will allow us to run the vpn server.

1. Click on services and look for EC2 under Compute.

2. Scroll down and select launch instance.

    ```
    You would select the amazon machine image you want from the list provided but the provided images only have the OS installed and that would take more time adding the required resources. but there is a better way.
    ```

3. On the left select AWS Marketplace
    > Here we will have images with already prconfigured tools.

4. search for openvpn and select the `free tier eligible` tag, to avoid charges. and hit the `Select` button. (allows only 2 connections)

5. Scroll down and select `continue`. on the loaded page select the `free tier eligable` instance and hit the `Review and launch` button and hit `launch` on the next page.

6. Next we will need a key pair that will authorise you to access the instance. If you have one already choose an existing if you dont then select `create a new  key pair`, give it a name and download then hit `launch instances` button.

    >be sure to remember the location of the downloaded file(filename.pem), we will need it later.

7. go to services and select EC2 and wait for it to be setup. once its set up it will show `running`.

8. Right click on the instance and select connect. This will display instructions on how to connect.

9. Scroll down and copy the line with ssh comamand under `Example`.

10. Launch the terminal/powershell and and move into the directory containing the downlaoded filename.pem file and paste the command. 

11. Type yes and hit enter.  the following propmts hit enter to retain the default settings unless you have a reason to change something. 

12. It will log you out and request you to login as `openvpnas` instead of root take note.
    > use the same ssh command you used ealier to login as openvpnas. in the command look for `root` and replace it with `openvpnas` and hit enter.

13. Lets set our own credentials. enter the command `sudo passwd openvpn` hit enter!.

14. Navigate back to the console where the instance is select it and copy the `IPv4 Public IP` address.

15. Open a new tab in the browser type https://ipv4adress:943/admin. 

> select advanced and and select proceed.

16. Login with the credentials username: openvpn(incase you didnt change the username) and the password you created. 

17. Navigate to VPN settings, scroll down under `Routing` select route all internet traffic through vpn. Scroll down and save settings then hit the `update running server` button.

**Thats it for the server** 



	continue
	free tier eligable t2.micro
	review launch
	launch
	choose existing key pair or create new one
	right click instance select connect