---
title: "Install, Configure, and  Host a Custom Website on Apache2  Web Server, with Ubuntu, Using AWS EC2 Instance"
seoTitle: "Step-by-Step Guide: Installing, and Configuring, an Apache2 webserver."
seoDescription: "Follow our comprehensive step-by-step guide for seamless installation, configuration, and deployment of your custom website."
datePublished: Thu Feb 22 2024 21:31:39 GMT+0000 (Coordinated Universal Time)
cuid: clsxqngcg000309l6hsxw63pi
slug: install-configure-and-host-a-custom-website-on-apache2-web-server-with-ubuntu-using-aws-ec2-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708204035980/90ca0459-6cc1-4b19-b0a8-1d9ad98b5734.png
tags: ubuntu, ec2, aws, apache, apache2, webserver, aws-ec2

---

## Introduction

Ubuntu provides the foundation and infrastructure necessary to run web server software like Apache2, enabling it to serve web content to clients over the internet.

We will be covering Installing, Configuring, and Hosting a Custom Website on Apache2 Web Server, with Ubuntu, Using AWS EC2 Instance.

## What you will need for this Hands-on

•AWS management console

•AWS EC2 Instance (free tier) . You can check the [pricing list](https://aws.amazon.com/ec2/pricing/?gclid=CjwKCAiA_tuuBhAUEiwAvxkgTjhwPjDJbSsyuUaPZC80TGMbUf2-QCfGWa5Ua7dsHN7quu7gs_x6eBoCpa0QAvD_BwE&trk=52f9267b-dca0-4589-9a8c-547fc84b784f&sc_channel=ps&ef_id=CjwKCAiA_tuuBhAUEiwAvxkgTjhwPjDJbSsyuUaPZC80TGMbUf2-QCfGWa5Ua7dsHN7quu7gs_x6eBoCpa0QAvD_BwE:G:s&s_kwcid=AL!4422!3!669047422248!e!!g!!amazon%20ec2%20price!20433874242!155026711889) here if you do not have a free-tier account

•GitHub account

## Setting up of EC2 Instance

1. Log into your AWS management console to begin this hands-on. Navigate to the EC2 instance by searching for the service in the console and click on it so you can create an instance. Click on 'launch instance'. I have marked it in a rectangular shape. Please take note of every area I emphasized with a circle or rectangle in the course of explaining this project.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708447699710/b79eb029-3f5c-4a03-9021-2bb6e24d40f1.png align="left")
    
2. After clicking on the 'launch instance', name your instance and then proceed to pick your Operating system (AMI) as Ubuntu. Make sure it is the free trier just like my screenshot so you do not incur costs while trying to set up.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708448372339/624c5421-c7c9-4265-9506-96d11a31d0c2.png align="left")
    
3. Proceed to create a key pair or use an existing key pair like I did. The key pair is used for secure SSH (Secure Shell) access to the instance. Scroll down to the security group and allow SSH traffic and HTTP traffic. I am emphasizing this because when I attempted this task severally, I kept getting errors when I tried to load my Apache2 on my web. This was because I did not allow for HTTP in my security group. No way that was going to work because enabling HTTP in your security group is crucial for ensuring that your web server can effectively communicate with clients and provide access to your online content and services in a secure and efficient manner. Go ahead to launch your instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708455739243/9d4299bb-13dd-42bf-bd37-84c43d573f35.png align="left")
    
4. After the instance created shows the ***running*** state, click on the check box, then proceed to click on connect.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708456799638/a168006d-f78f-4e0a-a945-b5b99168f444.png align="left")
    
5. Go ahead to "connect using the Instance Connect". Click on the orange button saying "Connect". You will be taken to a terminal.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708456980206/f4418405-e47a-4b9c-9db3-22f8abab151a.png align="center")

## Installing Apache2

One of the most extensively used open-source web servers in the world is Apache2, sometimes known as Apache HTTP Server or just Apache. The internet can receive web content thanks to Apache2. It is a well-liked option for hosting websites and web applications because of its great versatility, scalability, and customization. Web apps and dynamic websites are frequently made with Apache2. It is a reliable option for companies, organizations, and site hosts all around the world.

### Steps:

1. Run the command `sudo apt update` on your terminal to check for new updates. It should look like what is in the screenshot below.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708458136337/52238566-80a0-40c2-aa29-624a9c13f6cc.png align="center")
    
    Proceed to install Apache by running `sudo apt install apache2` command. You will see "Do you want to continue? \[Y/n\]". Type Y and press enter on your keyboard. You should see something like what is in the screenshot below. Copy the circled Public IP address and run it on your browser.
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708458583023/723a6f66-aec9-4bce-ba86-78e9857b1481.png align="center")
    
    Boom! You should have this page on your web after running your own unique Public IP address. Your IP address is not expected to look like mine. You would have your own unique address.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708458819465/80d49180-e835-4a47-9659-8e65f6f8ee46.png align="left")
    

## Hosting Custom Website on Apache2 Web Server.

1. Install git on your terminal first by running this command `sudo apt install git`. You should have something like what is in the screenshot below. We are installing git so that we use it to clone some codes from my [GitHub repository](https://github.com/Adaeze-69/Alt-School-Assignment-3.git) that we will use as our custom website. You can go ahead and click on the link and use it for this demonstration.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708462460953/4edc527b-b8f3-4507-b896-d2519573d6d9.png align="center")
    
    Create a folder next and name it whatever you want using the command `mkdir 'foldername'` , for example `mkdir adaeze` . This is the folder we will be putting our cloned git repository. Change your directory to the new folder created using the `cd` command. Something like `cd adaeze` since 'adaeze' is the directory/folder I created.
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708463240589/c932921e-f9d0-4c0f-8072-7d6800a7deb1.png align="center")
    
    Get any git repository with codes for a website or you can use [mine](https://github.com/Adaeze-69/Alt-School-Assignment-3.git). In the repository, click on the circled part that says 'code' colored green. Then copy to the clipboard using the button I circled as number 2.
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708462859798/bc74c597-d409-4fe9-af92-7e2ed2bbd9d7.png align="center")
    
    Go back to your terminal to clone the repository. the `git clone` command is an essential tool for getting a local copy of a remote Git repository. So it should look like this `git clone https://github.com/Adaeze-69/Alt-School-Assignment-3.git`
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708464377689/8cf6c280-05ad-4044-8c9f-09641ad64869.png align="center")
    
    Change the directory into the cloned repository. The command to run is `cd Alt-School-Assignment-3/` .This is the directory where all your codes are found. Your HTML and CSS codes you cloned. Remember that this directory is inside the 'adaeze' directory which has been your present working directory (pwd). See the screenshot below to understand better.
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708465647827/e2dceace-58d4-478c-babd-e7abcd212753.png align="center")
    
    Run `ls` command to see the list of files in the cloned directory.
    
7. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708466088957/dd4010cc-4807-4d63-9b3d-c41bb155786e.png align="center")
    
    Create another directory that will host your website. It should be like this: `sudo mkdir /var/www/newfilefolder` . Mine looks like this: `sudo mkdir /var/www/adaezennamdi` .
    
8. Next is to copy the content of everything in the present directory that you are. For me, `/adaeze/Alt-School-Assignment-3` is my present working directory, just like the screenshot. The '\*' is called a wild card which copies everything in that directory.
    
9. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708466475502/fa2657da-fc55-4b61-9aa1-153f6dd9e3fa.png align="center")
    
    Next is to `cd` into the new file folder you created and `ls` to be sure all the contents you copied are present there.
    
10. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708466694352/4aba3c79-f4cc-4cfa-9866-f835e896e07c.png align="left")
    
    Create a new 'conf' file with the command `touch` where you will move the default conf file into
    
11. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708517584067/123bf574-f7f0-4c28-a4f7-d00e2810e29a.png align="center")
    
    Copy contents of everything in the default conf file into the newly created 'conf' file which in my case is 'adaezennamdi.conf'. It should look like this `sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/adaezennamdi.conf` .
    
12. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708517913612/36d784ed-a6f5-489d-adc6-84946a351573.png align="center")
    
    Go ahead to edit the new 'conf' file you created using the command `sudo nano /etc/apache2/sites-available/adaezennamdi.conf`
    
13. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708518245832/08d52bf2-1f57-490e-bf69-5cac68823c23.png align="center")
    
    When you get into the nano editor, scroll down to **DocumentRoot**. Where you see 'adaezennamdi', you will see 'html'. Delete the 'html' and write the new name you gave to your folder you created in the `/var/www/foldername`. Mine is 'adaezennamdi' and that is why you see it there. After that, press 'ctrl O' on your keyboard to save, press the 'Enter' key, and then 'ctrl X' to exit the editor.
    
14. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708518394555/d1a27ba6-1e4a-4050-9c79-a678009216e9.png align="center")
    
    Enable your created custom new conf file with the command `sudo a2ensite adaezennamdi.conf`. Please, remember to use your own 'conf file' name you created and not mine.
    
15. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708518852782/75f1ceb8-a90d-4fa0-97a1-6c5cb09f56ea.png align="center")
    
    Disable the 'default conf file' `000-default.conf` whose contents were copied. The command should look like this `sudo a2dissite 000-default.conf` . If you do not disable this, your site will not load because this will still be running. Disabling it is necessary as this process will allow your enabled "Conf" from the previous steps to run efficiently.
    
16. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708519145910/5880ad1a-7940-4d12-88cb-0b223c8b9365.png align="center")
    
    At this point, you will need to reload your apache2 web server. To do that, type `sudo systemctl reload apache2` into your terminal.
    
17. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708519437720/9e5eb498-4082-4333-991e-57ba8ffc73eb.png align="center")
    
    On your web browser, revisit the Apache2 web server page (refer to step 4), process to reload it, and confirm if you have a similar snapshot with the image below (the image will be exact if you cloned my repository).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708519638391/4b8c701a-f42b-4c8c-b118-0d278356b057.png align="left")

1. Remember to terminate your AWS EC2 instance when you get to this point. Do not stop it but terminate. If you stop it, you will still incur costs from the Elastic Block Storage (EBS) Volume running with it. Terminate the EC2 instance. From the screenshots below, tick the checkbox, then click on the drop-down 'instance state' . You will see 'Terminate instance'. Click on it and it will redirect you to the page on the second screenshot. Click on 'Terminate' that is circled, and that is all.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708636435730/1fd412cd-7a07-4bd8-b708-c7f59d1ab3c6.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708636598234/34002643-504d-405b-a8d4-a46e9fe50a33.png align="center")
    
    ## Conclusion
    

Congratulations on completing the guide to Installing, Configuring, and Hosting a Custom Website on Apache2 Web Server, with Ubuntu, Using AWS EC2 Instance. While the process may have been challenging, your perseverance paid off. Remember, if you encounter challenges, seek help from documentation or online resources. You can also reach out to me on this platform too.

I hope you found value in this article and enjoyed the journey as much as I did creating it. Your dedication enriches our community. Keep exploring and innovating. Here's to your continued success!

Feel free to share your feedback and experiences. Best wishes on your future endeavors!