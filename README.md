# DevOps-Lifecycle
Project Description
Facebook just hired you as a Sr. Devops Engineer and they are looking to integrate a DevOps lifecycle for the latest version of Instagram website.
You have to implement this lifecycle as soon as possible.

Understand DevOps lifecyle and Git workflow
Understand Docker and writing of Dockerfiles
Good Knowledge of Jenkins and how to build Jenkins job
Knowledge of Virtual Machines
Knowledge of CI/CD pipleines

Hints
Git workflow should be lmplemented

Code build should be automatically triggered once a commit is made to the master branch or development branch

If a commit is made to master branch, test and push to production

If a commit is made to development branch, test but dont push to production

Containerize the code using a Dockerfile. The Dockerfile should be built eachtime there is a push to Github.

Once the website is buillt, design a test case that will basically check if the website can be opened or not. If yes, the test should pass.

Define the tasks above in a Jenkins pipleine with the following jobs

job1: Build the website

job2:Test

job3: Push to production
