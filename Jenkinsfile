pipeline {
    agent any
    stages {
        stage('Test Build') {
            steps {
                echo "Build sukses untuk ${env.BRANCH_NAME}"
            }
        }
    }
    post {
        success {
             sh '''
             curl -H "Content-Type: application/json" \
                  -x POST \
                  -d "{\"content\":\"Build SUCCESS untuk ${env. BRANCH_NAME}\"}"
                  https://discord.com/api/webhooks/1425909802210693321/EQj-k3Bbn5FaaE5UWL8aaaiFDpLoxE1rz3ipAclDxnBaK6vt3YjWnrmcpbEHTA9iF407
             '''
        } 
        failure {
            sh '''
             curl -H "Content-Type: application/json" \
                  -x POST \
                  -d "{\"content\":\"Build FAILED untuk ${env. BRANCH_NAME}\"}"
                  https://discord.com/api/webhooks/1425909802210693321/EQj-k3Bbn5FaaE5UWL8aaaiFDpLoxE1rz3ipAclDxnBaK6vt3YjWnrmcpbEHTA9iF407
             '''
        }
    }
}
