pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/asdfaaabbcc/saleor-platform.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t shivapaladugula/saleor-dashboard:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push shivapaladugula/saleor-dashboard:DEV'
            }
        }
    }
}