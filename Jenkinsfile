pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		git 'https://github.com/Sumantbag1992/Demo.git'
            	sh "./mvnw compile"
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
            	sh "./mvnw test"
                echo 'Testing...'
            }
        }
        stage('Package') {
            steps {
	   	sh "./mvnw package"	
                echo 'Packaging...'
            }
        }
        stage('Containerize') {
            steps {
	   	sh "docker build -t pet-clinic-image ."	
                echo 'Containerizing...'
            }
        }

        stage('Deploy') {
            steps {
            	sh "docker run -d -p 9090:9090 pet-clinic-image"
                echo 'Deploying...'
            }
        }
    }
}
