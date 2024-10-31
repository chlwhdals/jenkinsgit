pipeline {
  agent any
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/chlwhdals/jenkinsgit.git', branch: 'master'
      }
    }
    stage('image build & pull') {
      steps {
        sh '''
        sudo docker build -t chlwhdals264/keduitlab:red .
        sudo docker push chlwhdals264/keduitlab:red
        '''
      }
    }
    stage('delivery and deployment') {
      steps {
        sh '''
        ansible-playbook /var/lib/jenkins/node.yml
        pwd 
        '''
      }
    }
  }
}

