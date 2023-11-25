pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''#!/bin/bash
npm install'''
      }
    }

  }
  environment {
    registry = 'mariusz67/cicd_pipeline'
  }
}