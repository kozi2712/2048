pipeline {
    agent any

    stages { 
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
