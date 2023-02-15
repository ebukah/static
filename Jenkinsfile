pipeline{
  agent any 
  stages {
    stage ('Buildd') {
      steps {
        sh 'echo "Hello World"'
        sh '''
            echo "Multiline shell step works too"
            ls -lah
        '''
      }
    }
     stage ('Upload to AWS') {
        steps {
          withAWS(region:'us-east-1',credentials:'AKIA3Y5EIPXUA5PO4X73 (Static HTML publisher in AWS)') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsbucket042')
          }
        }
      }
  }
}
