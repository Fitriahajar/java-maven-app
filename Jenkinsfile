pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo "Building ${env.BRANCH_NAME}"
            }
        }
        stage('Test') {
            steps {
                echo "Testing ${env.BRANCH_NAME}"
            }
        }
        stage('Notify') {
            steps {
                script {
                    def status = currentBuild.currentResult
                    def webhookUrl = https://discord.com/api/webhooks/1427525796024684656/aYswnuRD0z6_8XXXWXaVDtIVhs0I1SZraNmVw0OIZuu6g0P8UL56QJkS0RJ9e6i52nhG
                    def message = "{\"content\": \"Build  ${env.BRANCH_NAME} status: ${status}\"}"
                    httpRequest httpMode: 'POST', contentType: 'APPLICATION_JSON', requestBody: message, url: webhookUrl
                }
            }
        }
    }
}
