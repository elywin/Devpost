---
layout: post
title: openVPN with AWS
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

4. search for openvpn

	select the free vpn
	continue
	free tier eligable t2.micro
	review launch
	launch
	choose existing key pair or create new one
	right click instance select connect