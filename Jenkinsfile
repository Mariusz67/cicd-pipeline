pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''
checkout scm
#!/bin/bash
npm install'''
      }
    }

  }
  environment {
    registry = 'mariusz67/cicd_pipeline'
  }
}