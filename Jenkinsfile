pipeline {
  agent any
  environment {
    nome = 'Rodrigo'
    // Dinamically created environment variables
    dinamico = """${sh(
      returnStdout: true,
      script: 'ip -4 a'
    )}"""
  }
  stages {
    stage('Build') {
      steps {
        echo "Esta é a build número ${env.BUILD_ID}"
        echo "Instância de nome: ${env.JENKINS_URL}"
        echo 'Esta é a minha primeira pipeline usando Jenkins'
        sh 'make'
        echo "${nome}"
      }
    }
    stage('Test') {
      steps {
        echo 'Estou rodando alguns testes'
        sh 'make check || true'
        //junit '**/target/*.xml'
        echo "${dinamico}"
      }
    }
    stage('Deploy') {
      environment {
        nome = 'svork'
      }
      when {
        expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS'
        }
      }
      steps {
        echo 'Ae, deu certo a build, vamos para produção!!1!'
        echo 'Fazendo o deploy com Ansible, Chef ou até mesmo Puppet'
        echo "${nome}"
      }
    }
  }
}
