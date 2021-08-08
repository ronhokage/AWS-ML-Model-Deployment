# AWS-ML-Model-Deployment
## <ins> Description </ins> ##
The aim of the work is to explain the deployment of a machine learning model in a Cloud premise. We are free to choose any of the cloud vendors in the market, here we have taken 
AWS as the one where our deployment be done. The API was flask by means of which we showcased our model to a HTML interface and then processed the same to AWS via WinSCP and Putty.
We look to see the Length of Stay for each patient on case by case basis so that the Hospitals can use this information for resource allocation. The length of stay is divided into 11 different classes ranging from 0-10 days to more than 100 days.
This use case belonged to a Hackathon and we like to see the final model when selected, can be deployed to the cloud.
The outcome of modelling rather than to find the best solution was more towards the final implementation and hence a decision tree model was taken forward.

## <ins> Approach </ins> ##
1)-First and foremost is the need of installing the required softwares:-

a)-Putty and Putty gen: Putty for configuring our hostname to AWS, with the required set of authorization. Putty gen is needed to generate primary key (this is saved as a pem file in your system). The primary key is generated for your pkl file, where you have initialized your model. 
b)-
