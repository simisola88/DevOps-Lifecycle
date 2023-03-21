pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'chineloDevOps', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''cd /home/chinelo/main
docker build -t simisol88/prodtest .''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/chinelo/main', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage('Test') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'chineloDevOps', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''#!/bin/bash
dockrid=$( docker ps --filter name=prodtest -qa)
if [$dockrid == \'\']
then
        docker run -p 898:80 -d --name prodtest simisol88/prodtest
else
        docker stop $dockrid  && docker rm $dockrid
        docker run -p 898:80 -d --name prodtest simisol88/prodtest
fi
if  curl -s localhost:898 | grep \'This post has three image\'
then
     echo "Test successful"
    exit 0
else
  echo "Test Failed"
  exit 1
fi''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/chinelo/main', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
