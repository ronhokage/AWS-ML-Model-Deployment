# AWS-ML-Model-Deployment
## <ins> Description </ins> ##
The aim of the work is to explain the deployment of a machine learning model in a Cloud premise. We are free to choose any of the cloud vendors in the market, here we have taken 
AWS as the one where our deployment be done. The API was flask by means of which we showcased our model to a HTML interface and then processed the same to AWS via WinSCP and Putty.
We look to see the Length of Stay for each patient on case by case basis so that the Hospitals can use this information for resource allocation. The length of stay is divided into 11 different classes ranging from 0-10 days to more than 100 days.
This use case belonged to a Hackathon and we like to see the final model when selected, can be deployed to the cloud.
The outcome of modelling rather than to find the best solution was more towards the final implementation and hence a decision tree model was taken forward.

## <ins> Approach </ins> ##

#### <ins> First things First </ins> ####

a)-Putty and Putty gen: Putty for configuring our hostname to AWS, with the required set of authorization. Putty gen is needed to generate primary key, it is also known as a key generator (this is saved as a pem file in your system). The primary key is generated for your pkl file, where you have initialized your model.

b)- WINScp: It is a free and open-source SSH File Transfer Protocol, File Transfer Protocol, WebDAV, Amazon S3, and secure copy protocol client for Microsoft Windows. Its main function is to secure file transfer between a local computer and a remote server. Here we have created our python app file which consists of the flask API calls, index file under templates where we designed our HTML template and finally our notebook which comprises of the analysis.

#### <ins> Configuring AWS </ins> ####
a)- Next step is a very important one ie accessing our cloud environment, AWS. We start of by creating an instance.An instance is already created named ML_Health_AV, which is running in an ubuntu server. While creating an instance we have a liberty to choose our options from ubuntu,linux,windows etc. as the host servers. After creation of the instance, you can view on which hostname, Ip address, IPV4 DNS etc. your'e instance is running upon.

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/instance_1.JPG)

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/instance_2.JPG)

b)- Before you launch your instance, you need to look upon the generation of your pem file. This is nothing but a key pair and is needed so that you can access your instance. Since we have selected ubuntu server as the one where our instance will be running it will be a ubuntu instance. This key pair is then saved as a pem file in your system, after you download via AWS.

c)- Click to connect on the instance you created and also see the security groups as you need to makesure that the connection you establish via WinSCP can connects to your cloud hassle free. For that, go to security groups and provide full access to the group your'e creating.(More detailed info on:- [How to create a instance?](https://www.cloudbooklet.com/create-an-ec2-instance-on-aws-with-ubuntu-18-04/))

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/sec.JPG)

#### <ins> Conversion of pem to ppk file </ins> ####
a)- The next process involves conversion of pem file a ppk (public private key pair) file. This is acheived by means of putty gen. Once done,click on save private key option in putty gen and it will save this file in your system. 
![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/Pgenfile.JPG)

#### <ins> Transfer of files </ins> ####

a)- We want to make sure to transfer our model and deployment files to AWS, for that Winscp assits us to transfer the required files from local system.
- Login page

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/WIN_SCP_F2.JPG)

- Also you need to provide your ppk file in the authentication file in order to connect successfully.

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/Authfile.JPG)

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/Win_SCP%20files.JPG)

b)- Now if we want to check whether the files has been transfered to the cloud or not, we can check through Putty.

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/putty_check.JPG)

#### <ins> Running your file </ins> ####
a)- When the required files has been set in we can run the python file to see the deployment, however there are few things to keep in mind. We need to keep the port as 8080,
which needs to be configured in the python file. After that, run your python file in putty.
![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/deploy_1.JPG)

b)-You can see the public Ip4 DNS in your AWS instance details, copy that and paste to your browser. Also, mention the port number after the hostname and you can see your deployed file.

![text](https://github.com/ronhokage/AWS-ML-Model-Deployment/blob/main/Img/Deploy_3.JPG)
