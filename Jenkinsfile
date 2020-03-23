pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello World!"'
        sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
<<<<<<< HEAD
             }
         }
         stage('Security Scan') {
              steps { 
                 aquaMicroscanner imageName: 'alpine:latest', notCompleted: 'exit 1', onDisallowed: 'fail'
              }
         }         
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-2',credentials:'aws-static') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'static-jenkins-pipeline')
                  }
              }
         }
     }
}
=======
      }
    }

    stage('Security Scan') {
      steps {
        aquaMicroscanner(imageName: 'alpine:latest', notCompleted: 'exit 1', onDisallowed: 'fail')
      }
    }

    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-east-2', credentials: 'aws-static') {
          sh 'echo "Uploading content with AWS creds"'
          s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file: 'index.html', bucket: 'static-jenkins-pipeline')
        }

      }
    }

  }
}
>>>>>>> 7585a63a3013fabb1c87201036157b4b2656b7c1
