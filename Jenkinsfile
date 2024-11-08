pipeline {
  agent any
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/chlwhdals/jenkinsgit.git', branch: 'master'
      }
    }
    stage('docker build and push') {
      steps {
        sh '''
        sudo docker build -t chlwhdals264/keduitlab:red .
        sudo docker push chlwhdals264/keduitlab:red
        '''
      }
    }

  }
}
