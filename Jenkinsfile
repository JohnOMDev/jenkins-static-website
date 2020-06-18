pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'eu-central-1') {
                    sh 'echo "hello World uploading with aws credential"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'johnjenkins')
       
                }
            }
        }
    }
}         
                
