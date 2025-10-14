pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Building ...'
                dir('java-maven-app') {
                    sh 'mvn clean install'
                }
            }
        }
        
        stage('test') {
            steps {
                echo 'Testing ...'
                dir('java-maven-app') {
                    sh 'mvn test'
                }
            }
        }
    }
} 
