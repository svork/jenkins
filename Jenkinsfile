pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Esta é a minha primeira pipeline usando Jenkins'
        sh 'make'
      }
    }
    stage('Test') {
      steps {
        echo 'Estou rodando alguns testes'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Fazend o deploy com Ansible, Chef ou até mesmo Puppet'
      }
    }
  }
}
