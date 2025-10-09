pipeline {
    agent any

    tools {
        maven 'maven-3.9'
    }

    stages {
        stage('Build jar') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Build Image') {
            steps {
                script {
                    echo "Building the Docker image..."
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-credential', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        sh 'docker build -t fitria15/java-maven-app:jmp-2.0 .'
                        sh "echo \$PASS | docker login -u \$USER --password-stdin"
                        sh 'docker push fitria15/java-maven-app:jmp-2.0'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
