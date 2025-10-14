pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Building ...'
                sh 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                echo 'Testing ...'
                sh 'mvn test'
            }
        }
    }
} 
