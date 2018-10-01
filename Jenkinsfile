pipeline {
  agent any
  parameters {
    string(name: 'nome', defaultValue: 'Rodrigo', description: 'Digite seu nome')
    text(name: 'txt01', defaultValue: 'Uma linha\nOutra linha', description: 'Texto aleatório')
    booleanParam(name: 'status_maquina', defaultValue: false, description: 'Liga/Desliga')
    choice(name: 'marcha', choices: ['Primeira', 'Segunda', 'Ré'], description: 'Marchas do Carro') 
    file(name: 'arquivo', description: 'Escolha um arquivo para fazer upload')
  }
  options {
    timestamps()
  }
  stages {
    stage ('First, we build') {
      steps {
        echo "The first step should be building"
      }
    }
    stage ('Then, we test') {
      steps {
        echo "Test driven development, way to go"
      }
    }
    stage ('Show Parameters') {
      steps {
        echo "Nome: ${params.nome}"
        echo "Texto Aleatório: ${params.txt01}"
        echo "Ligado: ${params.status_maquina}"
        echo "Marcha: ${params.marcha}"
      }
    }
  }
  post {
    success {
      echo "Yay, we are good"
    }
    failure {
      echo "Ops, we messed up" 
    }
  }
}
