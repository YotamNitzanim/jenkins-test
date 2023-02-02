/*Jenkinsfile (Declarative Pipeline)*/
/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'ubuntu:latest'
                     args '-u root:root' } }
    stages {
        stage('build') {
            steps {
                sh 'ls'
            }
        }
        stage ('Deploy') {
        steps {
            sh 'apt-get update'
            sh 'apt-get install openssh-client -y'
            sh 'scp deploy.sh ${ec2-user}@${54.199.250.191}:~/'
            sh 'ssh ${ec2-user}@${54.199.250.191} "chmod +x deploy.sh"'
            sh 'ssh ${ec2-user}@${54.199.250.191} ./deploy.ssh'
        }
    }
    }
}
