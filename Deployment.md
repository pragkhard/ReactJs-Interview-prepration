How to deploy Vite React App on AWS S3

💬 "To deploy a Vite React app on AWS S3, I first build the project using npm run build, then create an S3 bucket and enable static hosting. After uploading the dist/ files and setting permissions, the site is accessible via the S3 endpoint. For better performance, I can integrate CloudFront with HTTPS support."

Steps
1.Build the project: npm run build
2.Create an S3 bucket & enable Static Website Hosting
3.Upload dist/ files to S3
4.Set public access permissions
5.Access the website using the S3 URL

-----------------------------------------------------------------------------------------------------

Deploy React App on AWS S3 | Amazon Route 53 | Amazon CloudFront or Build and deploy ReactJs App using Jenkins Pipeline | Deploy ReactJS app to AWS S3 Which approach is good to deployment?
💬 "For small React apps, I prefer deploying to AWS S3 with CloudFront for caching and Route 53 for domain management. However, for large projects with frequent updates, Jenkins CI/CD is better, as it automates builds, deployments, and cache invalidation, ensuring a smooth DevOps workflow."

How to set up a Jenkins CI/CD pipeline to automatically build and develop a ReactJs App from Github to Amazon S3

Steps-
1.	ReactJS project stored in a GitHub repository
2.	Go to Jenkins server -> Dashboard -> new item -> Enter the item name (reactjs-ci-cd) -> Click on pipeline -> Click OK -> Go to pipeline -> Go to script -> Lets generate hello world (there is an drop down) -> In stage one just checkout the code (‘Git Checkout’) -> Copy git repo url -> and pasted in stage steps {git url:”https://....”} and passing argument with URL branch :”main” because this repo is public not configure the credentials -> Save the job -> click build now
Successfully checkout the source code.

 we need nodejs on Jenkins, Setup nodejs on jenkins– because in the background uses npm
node package manager
Go to dashboard -> Manage Jenkins -> manage plugins ->Available plugins->Search and select nodejs ->Select install without restart-> wait for the installation to finish-> Manage Jenkins ->Global tool Configure ->Scroll down the page select nodejs installations ->Select install automatically ->Select version->Save->
 This tool configuration takes care of installing NodeJS on Jenkins 
Go to dashboard -> open react JS cicd application ->configure -> after checkout I want the use npm install but I need to keep nodejs in the class path open pipeline syntax -> select declarative directive generator-> select tools->select nodejs->Click on generate declarative directive -> copy the code ->pasted to the pipeline script (what it does is it'll add nodejs installation to the path so that we can run npm commands)-> create new stage so we should do npm install (so that required dependencies are installed)-> run the command using ‘sh’ step npm install->save->build now

let's move on to next stage
 go to the job configure -> go to pipeline -> now I want to build and get disc folder which contains uh HTML stuff that I need to deploy into S3 bucket-> the command to build reactjs application using npm is “npm run build” remember this generates disc folder inside that folder -> add one more stage let's name this S3 deploy to deploy applications onto S3 and we are going to use S3 sync command which is going to sync all the files in disc folder into S3 bucket ->  for syncing files to S3 bucket Jenkins must have permissions to S3 because Jenkins is running on ec2 instance

let's go and create IAM Roles attach IAM Ro to Jenkins ec2 instance
Login AWS-
Go to IAM-> Click on roles->Create role-> I’m creating this role for ec2 instance select E2
Instance-> use case also select ec2 instance->Next-> select permissions policies (it is better to create custom policy so that we will not have any security issues and configure it)-> search and select  S3 full access (please don't try this in real world you must create a policy with only required)-> Go next-> give a name-> create the role-> go to ec2 dashboard-> select the instance-> actions-> security-> modify IAM role-> select S3 deploy ->update IAM role->

Jenkins is on ec2 ec2 has S3 full access
it also has AWS CLI commands installed generally default AC instances we launch it will have AWS CLI pre-configured -> let's run the command S3 CLA command (aws-s3 sync dist/ s3://) 
after npm run build it creates disc folder so I want to sync all the content inside disc
folders dis

we need to go and configure S3 bucket
Go to AWS console ->S3-> Click buckets->create bucket->bucket name (jhc-react-app)->Click on create bucket ->select jhc-react-app

 we should enable static website hosting I mean all of you might be knowing S3 allows static website hosting that is what we're trying to do in this example-

go to properties-> scroll completely down you'll find static website -> click on edit-> enable-> It'll ask for index document we have index.html inside this folder (that
should be the index document)-> when I put just S3 URL this page is by default loaded ->save it
after enabling static website hosting we need to configure permissions so that S3 bucket will give get access otherwise customers cannot access this website

edit block Public Access -> uncheck this save-> confirm and go to bucket policy click on edit-> AWS documentation for creating bucket policy for host posting static website copy this pastes here(S3 bucket policy) add the bucket name in the policy(jhc-react-app)->save changes
react app save changes perfect S3 bucket is ready now

we need to push elements inside dis folder from Jenkins to S3 that finishes deploying static website 

Let's go to Jenkins pipeline code let me take bucket name it is jhc-react-app in the end use hyphen hyphen delete we are using this delete option because in S3 we want only the contents of dis folder that's reason we are using hyphen hyphen delete so that what we are syncing only those files will be there in S3 (aws-s3 sync dist/ s3:// jhc-react-app --delete)->save and build now

let's go to S3 bucket -> go to properties-> open website URL (it is successfully deployed)
let's make a small change and redeploy

go to git have repository src so let me find way to make a change this one hello world let's replace demo with Java home click on edit commit the change commit we made changes to the code let's go to Jenkins job build it it should deploy the changes we made let's go and check console output perfect I'm refreshing it is getting deployed 

🎯 Problem Statement
We need to automate the deployment of a ReactJS application hosted on AWS S3 using Jenkins CI/CD pipeline.
________________________________________
✅ Steps to Implement CI/CD Pipeline
1️ Code Setup in GitHub
•	The ReactJS project is stored in a GitHub repository.
•	Jenkins will pull the latest code before each deployment.
2️ Setting Up Jenkins for React CI/CD
•	Create a new Jenkins pipeline job.
•	Install Node.js plugin on Jenkins for running npm commands.
•	Define pipeline script that checks out the GitHub repo.
3️ Install Dependencies & Build React App
•	Use npm install to install all dependencies.
•	Run npm run build to generate the dist/ folder (contains the static website files).
4️ Deploy to AWS S3
•	Create an S3 bucket & enable Static Website Hosting.
•	Configure Bucket Policy & Public Access Settings.
•	Sync dist/ folder to S3 using: 
                   bash
CopyEdit
aws s3 sync dist/ s3://your-bucket-name --delete
•	Ensure Jenkins EC2 instance has IAM Role with S3 permissions.
5️ Verify Deployment
•	Copy & open the S3 website URL in a browser.
•	Make changes in GitHub → Jenkins detects changes → Auto-deploys to S3
•	Jenkins (for CI/CD automation)
•	AWS S3 (for static hosting)
•	AWS IAM (for access control)
•	AWS CLI (for deployment commands)
•	GitHub/GitLab (for source code)
•	EC2 (Jenkins Server) (to run the pipeline)

💬 In my previous projects, I automated ReactJS deployments using Jenkins pipelines. The process involved pulling the latest code from GitHub, installing dependencies, building the project, and syncing the dist/ folder to an AWS S3 bucket. To ensure secure and automated deployments, I used an IAM role with S3 permissions and AWS CLI for syncing files. This CI/CD pipeline helped us achieve faster, error-free deployments with minimal manual effort.

---------------------------------------------------------------------------------------------------

1️⃣ Configure the Jenkins Pipeline
"Whenever a new commit is made, Jenkins automatically triggers the pipeline to initiate the build and deployment process."

2️⃣ Build React App
"In the pipeline, we configure Jenkins to first run npm install to install all project dependencies.
 Then, npm run build generates a production-ready build in the build/ directory."

3️⃣ Prepare S3
"We create an AWS S3 bucket and enable Static Website Hosting.
 We also configure the necessary permissions to allow public access."

4️⃣ Deploy to S3
"Using the AWS CLI, we sync the build/ folder with the S3 bucket using:


5️⃣ Access the App
"Once deployed, the app is accessible via the S3 URL."






































