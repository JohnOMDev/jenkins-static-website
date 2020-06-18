pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'echo "hello World">index.html'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'johnjenkins')
       
                }
            }
        }
    }
}         
                
