pipeline {
  agent any
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
