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
        sh 'make check || true'
        //junit '**/target/*.xml'
      }
    }
    stage('Deploy') {
      when {
        expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS'
        }
      }
      steps {
        echo 'Ae, deu certo a build, vamos para produção!!1!'
        echo 'Fazendo o deploy com Ansible, Chef ou até mesmo Puppet'
      }
    }
    stage('Print some strings') {
      // Let's create some string
      def nome = 'Rodrigo'
      echo 'My name is ${nome}'
      echo "My name is ${nome}"
    }
  }
}
