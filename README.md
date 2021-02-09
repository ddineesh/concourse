# Configure access to your local Concourse CI with the name dinesh-ci, using username admin and password admin
fly --target dinesh-ci login --concourse-url http://127.0.0.1:8080 -u admin -p admin

# Register the new pipeline:

fly -t dinesh-ci set-pipeline -p hello-world -c hello.yml

# After the above executed successfully, we will the below output

pipeline created!
you can view your pipeline here: http://127.0.0.1:8080/teams/main/pipelines/hello-world

Our hello-world job does not have any input triggers, so we must manually start it.

Click the "hello-world" job to view it, 
and click its Plus (+) button on the top right to manually trigger the job to start. 


# The pipeline is currently paused. to unpause, either: run the unpause-pipeline command:
fly -t dinesh-ci unpause-pipeline -p hello-world

# The below command will help us to execute the job

fly -t dinesh-ci execute -c  C:\Dinesh\Software\concourse\jobs\basic\task-hello-world\task_ubuntu_uname.yml

# To input the job 

fly -t dinesh-ci execute -c  C:\Dinesh\Software\concourse\jobs\basic\task-inputs\inputs_required.yml -i some-important-input=.


# Concourse Tutorial

Learn to use https://concourse-ci.org with this linear sequence of tutorials. Learn each concept that builds on the previous concept.

Read the tutorial at https://concoursetutorial.com

## Thanks

Thanks to Alex Suraci for inventing Concourse CI, and to Pivotal for sponsoring him and a team of developers to work since 2014.

At Stark & Wayne we started this tutorial as we were learning Concourse in early 2015, and we've been using Concourse in production since mid-2015 internally and at nearly all client projects.

Thanks to everyone who has worked through this tutorial and found it useful. I love learning that you're enjoying the tutorial and enjoying Concourse.

Thanks for all the pull requests to help fix regressions with some Concourse versions that came out with "backwards incompatible change".

## Getting Started

Read the tutorial at https://concoursetutorial.com  

https://concoursetutorial.com/basics/task-inputs/

## Local development of tutorial

This tutorial is built using [`mkdocs`](http://www.mkdocs.org/). Once installed, you can continuously build and serve the tutorial locally with:

```plain
mkdocs serve
```

View the site and live changes at https://localhost:8000.

