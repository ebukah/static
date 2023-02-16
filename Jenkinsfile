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
    stage ('Lint HTML') {
        steps {
          sh 'tidy -q -e *.html'
        }
    }
     stage ('Upload to AWS') {
        steps {
          withAWS(region:'us-east-1', credentials:'aws-static') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsbucket042')
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'indexx.html', bucket:'jenkinsbucket042')
          }
        }
      }
  }
}
