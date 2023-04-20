pipeline {
    agent any

    stages { 
	stage('Build') {
		steps {
		       nodejs('Node20'){
			    sh 'apt-get -y install python python2.7 python-pip python-dev build-essential'
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
