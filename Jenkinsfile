/*Jenkinsfile (Declarative Pipeline)*/
/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.10.7-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
        stage ('Deploy') {
        steps {
            sh 'yum -y install openssh-clients'
            sh 'scp deploy.sh ${ec2-user}@${ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com}:~/'
            sh 'ssh ${ec2-user}@${ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com} "chmod +x deploy.sh"'
            sh 'ssh ${ec2-user}@${ec2-54-199-250-191.ap-northeast-1.compute.amazonaws.com} ./deploy.ssh'
        }
    }
    }
}
