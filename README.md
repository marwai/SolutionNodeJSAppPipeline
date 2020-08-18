# CONTINUOUS INTEGRATION AND DEPLOYMENT WITH JENKINS PROJECT

Look at he [CICD README](CICD.md) for more information 

Before Jenkins| After Jenkins 
-----|------
Developers complete assignments, commit code at same time. Later, build is tested and deployed| Code is built and tested as soon as Developer commits code. Jenkins builds and tests code many times during the day. If the build is successful, Jenkins will deploy the source into the test server and notifies the deployment team. If build fails, Jenkins will notify the errors to the developer team.
Developers wait until other developers finish coding to check their build.| The code is built immediately after any of the Developer commits
Difficult to isolate, detect, fix errors for multiple commits| Code is built after each commit of a single developer, easy to detect whose code caused built to fail.
Code build and test process are manual| Automated build and test process, saving time and reducing defects
Code is deployed once all errors are fixed and tested|Code is deployed after every successful build and test
Dev Cycle is slow| The dev cycle is fast. New Features are more readily available to users. Increase in profit. 


## Creating CI/CD Pipeline

- First create a Webook for a repository. Go into the Repo settings > Webhooks > add Webhook

![1st step](images/1st%20step.png)
### Then add the payload URL, use the webapp URL:
```http://18.132.46.105:8080/github-webhook/```



![2nd step](images/2nd%20step.png)

## Continues Integration 

### 1) First click on the ```new item``` as seen below 
![3rd step](images/3rd%20step.png)

### 2) Enter the name of the project and select the Freestyle project type
![4th step](images/4th%20step.png)

### 3) Enter the configurations 

### 4) Next, test the build by clicking build now. The build will appear in build history. The build is started when you 
```git push``` to Github 
![5th step](images/5th%20step.png)

### 5) If the build is successful, there should be 3 passes! Any errors can be found in the console output
![6th step](images/6th%20step.png)

### Continuos Deployment (CD) 
#### Similarly to the CI job, CD is created, create an appropriate name such as ```name deploy job```

#### The major difference between this and the CI is the execute command shell, please insert the following: 
![7th_step](images/7th%20step.png)

#### Again, build on the __CI JOB__ this will automatically pass the build to this CD job if succesful
![8th_step](images/8th%20step.png)

![9th_step](images/9th%20step.png)



)