pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }
         stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
         }
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
                
