# Deploy a private s3 bucket static website using CloudFront

## `Objective:`

> Create a static website and host it on S3 bucket(private bucket) but with public read policy assigned, using cloud front for CDN.

## Overview Of Task Execution

- In this Document i'll outline the steps required to deploy a static website hosted on a private s3 bucket on AWS and using CloudFront as CDN to display the web contents

## Tasks:

## `s3 Bucket setup`

1. Login to your AWS account and search for `s3`

![s3 service](img/s3-service.jpg)

2. After clicking on the `s3` it will take you to a new page

> Then click on `Create bucket`

![s3 service](img/s3-page.jpg)

3. Enter a unique bucket name and click on `Create bucket`

![s3 service](img/bucket-name.jpg)

![s3 service](img/bucket-create.jpg)

> > The `Block public access` is what tells if your bucket is publicly or privately accessible. It blocks public access by default(private).

![s3 service](img/block-public-access.jpg)

> Leave all default settings

4. Your bucket has been created now you can upload your static website files.

![s3 service](img/s3-created.jpg)

5. Click on your bucket name and then navigate to the `Upload` button to upload your files from your file explorer

![s3 service](img/s3-files-uploaded.jpg)

> Now thats all we have to do for now.

## `Lets configure our CloudFront to render our website files`

6. Search for CloudFront and click on it

> You will be taken to a new page and then click on `Create a CloudFront distribution`

![s3 service](img/cloudfront-page.jpg)

7. Click on the `Origin domain` text area
   > Your s3 bucket name should pop up for you to select

![s3 service](img/create-dist.jpg)

8. After selecting your bucket name scroll down to `Origin access` and select `Origin access control settings(recommended)`

![s3 service](img/OAC.jpg)

> Click on `Create new OAC` and select your bucket name if your s3 bucket name does not appear on the dropdown options then click on create

![s3 service](img/create-oac.jpg)

> > This will create a policy you can attach to your s3 bucket policy permission so CloudFront can read your website contents and serve them.

> > Sroll down and click on `Create distribution`

![s3 service](img/create-cloudfront-dist.jpg)

9. Our CloudFront distribution has been created. Now let's copy the policy that will give CloudFront access to read our s3 bucket static website files. Click on `Copy Policy`

![s3 service](img/dist-created.jpg)

10. Let's go back to our s3 bucket permissions tab

![s3 service](img/bucket-policy.jpg)

> Search for `Bucket policy` and click on `Edit`

> > Now paste the policy you just copied and save

![s3 service](img/paste-policy.jpg)

11. Go back to your created CloudFront distribution and copy your `distribution domain name`

![s3 service](img/dist-created.jpg)

12. Paste on your browser to view your static website

![s3 service](img/access.jpg)
