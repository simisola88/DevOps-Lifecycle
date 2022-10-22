pipeline {
    agent any

    stages {
        stage('Deploy Instagram Demo') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'Prods-apache', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/', remoteDirectorySDF: false, removePrefix: '**/*Jenkinsfile', sourceFiles: '**/*.jar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
