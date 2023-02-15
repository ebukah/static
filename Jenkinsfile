pipeline{
  agent any 
  stages {
    stage ('Upload TO AWS') {
      steps {
        sh 'echo "Hello World"'
        sh '''
            echo "Multiline shell step works too"
            ls -lah
        '''
      }
    }
  }
}
