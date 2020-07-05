# Infviz demo for generated documents on pull request
## Overview
This is a demo which will generate documents on a pull request. It will put links to the generated documents back in the pull request comments. This works with codecommit, codebuild and cloudformation files.

## What's included
This section will describe the files included:
* codeBuild.yaml - This is a cloudformation file that will setup codebuild, cloudwatch events and lambdas which will perform the generation of the documents.
* demo.yaml - This is a sample cloudformation file which has the resources that will be documented in the demo.
* demo-params.json - This is a sample parameters override file that is compliant with aws cloudformation deploy command line.
* sampleSpec.yaml - This is a sample code build spec file.

## Setup
This section will outline the steps to run the demo.
1. Contact info@infviz.io to get your infviz keys.
1. In your AWS account create a new codecommit repository. Get the HTTPS clone url and arn of the repository.
1. On your local machine clone the new repository.
1. On your local machine create a new branch and copy the following files
    * demo.yaml
    * demo-params.json
    * sampleSpec.yaml
1. On your local machine push the new branch back to your repository.
1. In your AWS account deploy the codeBuild.yaml file. Use the infviz keys, codecommit url and arn.
1. Once the deployment has finished. Create a new pull request from your branch to master.
1. In the Pull Request activities tab you should see a new comment indicating your build has started.
1. Once codebuild has finished you will see the generated files listed in your Pull Request activities tab.