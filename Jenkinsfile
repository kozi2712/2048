pipeline {
    agent any

    stages {
        
        stage('Clone Repo') {
            steps {
                script{
                    checkout([$class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[url: 'https://github.com/kozi2712/2048']]])
            		
                }

            }
        }
        stage('Build') {
            steps {
                script{
			nodejs('Node-18.14'){
                    		echo 'Clean cache'
                   		sh 'yarn cache clean'
                   		sh 'yarn install'
               		}
                }

            }
        }
        stage('Test') {
            steps {
                script{
			nodejs('Node-18.14'){
                		sh 'yarn test'
                		}
                }

            }
        } 
        stage('Deploy') {
            steps {
                script{
			        echo 'Stage deploy'
                }

            }
            
            
        }
    }
}
