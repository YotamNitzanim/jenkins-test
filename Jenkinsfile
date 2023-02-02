/*Jenkinsfile (Declarative Pipeline)*/
/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'ubuntu:latest'
                     args '-u root:root' } }
    environment {
        FLASK_APP = 'flaskr'
        FLASK_ENV = 'development'
    }
    stages {
        stage('build') {
            steps {
                sh 'ls'
            }
        }
        stage ('Deploy') {
        steps {
            sh 'apt-get update'
            sh 'apt-get install openssh-client'
            sh 'scp deploy.sh ec2-user@ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com:~/'
            sh 'ssh ec2-user@ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com "chmod +x deploy.sh"'
            sh 'ssh ec2-user@ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com ./deploy.ssh'
        }
    }
    }
}
