pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh '''
checkout scm
'''
      }
    }

  }
  environment {
    registry = 'mariusz67/cicd_pipeline'
  }
}