---
layout: post
title: Cloud storage S3 (AWS)
---

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. It can be used to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics.

Now that we know what Amazon S3 is lets configure an Amazon S3 storage.

We are gong to:
- Create and configure bucket
- Upload objects
- View objects
- Copy/move objects
- Delete objects
- Delete bucket

Step 1

Login to the AWS management console, select services and locate S3 under Storage.

On the S3 dashboard select create bucket 

Give your S3 bucket a name and choose a region closest to where your clients are located or near your location if its for personal use.

By default AWS S3 will block all public access to the newly created bucket and the objects we upload to it and will prevent us from accidentally granting access to them later ia access control lists or S3 bucket policies. 

**Note:** ` recomand that you leave the "Block all public access" setting turned ON`. Enabling access to a bucket should only be done when it is absolutely necessary instead use S3 bucket Policies or S3 Access Points to grant limited access to S3 buckets and indiidual objects within.

Click create bucket.

Bucket is successfully created.
Click on the newly created bucket name.

Select `upload`

Select `Add files`

Scroll down there is a Permissions drop-down. Here you can set permissions on the uploaded object. With the defualt settings, any AWS user or roles within "this" account will be able to access these files as long as their AWS identity and Access Managment policy allows it.

Scroll down and Click on `upload`

To see more details about the objects uploaded click on one of them.

The `Object url` at the bottom is the Amazon S3 URL for this specific object but since we did not enable public access you cant use it. In this case the only way to view an uploaded object would be through the `Open`, or `Download` which automatically generate a temporary signed URL that grants us access to an object for a fe mins(5 mins) before expiring.   
