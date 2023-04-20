pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[url: 'https://github.com/kozi2712/2048']]])
            }
        }
        stage('Build') {
            steps {
                nodejs('Node20'){
                    echo 'Clean cache'
                    sh 'yarn cache clean'
                    sh 'yarn install'
                }
            }
        }
        stage('Run tests') {
            steps {
                nodejs('Node20'){
                sh 'yarn test'
                }
            }
        }
    }
}
