pipeline {

     agent any

	// agent {
		 // label 'linux-agent'
	// } 

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Imtiyaj5791/jenkins-flask-demo.git'
            }
        }

        stage('Build') {
            steps {
                
		sh 'docker compose build'
            }
        }

        stage('Test') {
            steps {
                sh 'docker compose up -d'
				sh 'sleep 60'
                sh 'curl -f http://localhost:5000'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}

//second
