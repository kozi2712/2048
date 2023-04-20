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
		       nodejs('Node20'){
			    sh 'yarn cache clean'
			    sh 'yarn install'
			}

		}
	}
	    
        stage('Test') {
            steps {
                nodejs('Node20'){
                sh 'yarn test'
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
