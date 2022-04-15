Deploy sample Node.js App in AWS elastic beanstalk through AWS code pipeline 

2022-01-05 
========================================  

Package Contents
========================================  

a. musician-app-master  
b. readme.md 

a. Configure AWS Elastic Beanstalk
=============================================  

Navigate into Elastic Beanstalk from AWS console 

1. Select ``Environments`` and choose the option ``Create a new environment``.

2. Choose ``Web server environment`` and  Click ``Select``.

3. Enter ``Application name``,``Environment name``,Click ``Managed platform``,Choose "Platform" ``Node.js``, Choose "Platform branch" ``Node.js running on 64bit Amazon Linux``,Choose "platform version" ``4.17.16(recommended)``, Choose "Node.js version" ``12.22.2``.

4. Click ``sample application`` and Click ``Create environment``.

   

b. Configure AWS Code Pipeline 
========================================  

Navigate into Code Pipeline from AWS console

1. Select ``Create new pipeline`` 
2. Enter ``Pipeline Name`` Click ``Service role`` and  Choose ``New service role``.
3. ``Role name`` Check box ``Allow AWS Code Pipeline to create a service role so it can be used with this new pipeline``.  Click ``Next``
4.  In Add source stage, Select "Source provider" ``Git hub (Version1)``, Click ``Connect to GitHUb`` give your github credentials.
5. Select  "Repository" ``Musician-App`` and "Branch" ``master``, In "Change detection options" Select ``GitHub webhooks (recommended)``. Click ``Next``.  
6. In Add build stage ,Click ``Skip build stage``.
7. In Add deploy stage Select "Deploy provider" ``AWS Elastic Beanstalk``, "Region","Application name"(which is given in elastic beanstalk),"Environment name"(which is given in elastic beanstalk).Click ``Next``
8. Click ``Create pipeline``
