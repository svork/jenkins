pipeline {
  agent any
  stages {
    stage('Suco de Laranja') {
      steps {
        echo "Suco de Laranja"
      }
    }
  }
  post {
    always {
      mail to: costa9rodrigo@gmail.com, subject: "Suco de Laranja"
    }
  }
}
