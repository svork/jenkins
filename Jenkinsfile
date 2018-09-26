pipeline {
  agent any
  parameters {
    string(name: 'Faculdade', defaultValue: 'USP', description: 'Nome da sua faculdade')
  }
  environment {
    nome = 'Rodrigo'

    // Dinamically created environment variables
    dinamico = """${sh(
      returnStdout: true,
      script: 'uname -a'
    )}"""

    // Using credentials
    user = credentials('teste')
  }
  stages {
    stage('Build') {
      steps {
        echo "Esta é a build número ${env.BUILD_ID}"
        echo "Instância de nome: ${env.JENKINS_URL}"
        echo 'Esta é a minha primeira pipeline usando Jenkins'
        sh 'make'
        echo "${nome}"
        echo "O nome da minha faculdade é: ${params.Faculdade}"
      }
    }
    stage('Test') {
      steps {
        echo 'Estou rodando alguns testes'
        sh 'make check || true'
        }
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
        echo "O meu usuário é: ${user_USR}"
        echo "O meu senha é: ${user_PSW}"
      }
    }
    post {
      always {
        //junit '**/target/*.xml'
        echo "${dinamico}"
      }
     failure {
        mail to: costa9rodrigo@gmail.com, subject: 'Pipeline has failed'
    }
  }
}
