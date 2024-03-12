Based on "cleanup-cloudformation" parameter
this pipeline will do UI deployment in AWS cloudformation or 
sync deployment files to s3 bucket and invalidate cloudfront 
This pipeline will do the following steps:
  - Using the git-clone catalog Task to clone the UI source Code
  - It will do build the UI code , and create the deployment artifacts that need to be copied to S3
  when "cleanup-cloudformation" parameter is true
  - Then it will git clone the deployment source code 
  - It will copy the build artifacts into the www folder in deployment workspace.
  - It will then invoke the cloud formation template using aws cli
when "cleanup-cloudformation" parameter is false
  - sync UI code to s3 bucket
  - Run cloudfront invalidation

Ref to appkube-standalone-ui-deployment repo for AWS cloudfromation details
