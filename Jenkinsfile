pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''#!/bin/bash
npm install'''
      }
    }

    stage('Test') {
      steps {
        sh '''#!/usr/bin/env sh
echo \'The following "npm" command (if executed) installs the "cross-env"\'
echo \'dependency into the local "node_modules" directory\'
set -x
# npm install --save-dev cross-env
set +x
echo \'The following "npm" command tests that your simple Node.js/React\'
echo \'application renders satisfactorily\'
set -x
npm test'''
      }
    }

    stage('Deploy') {
      steps {
        script {

          def customImage = docker.build("mariusz67/cicd_pipeline:${env.BUILD_ID}")

          docker.withRegistry('https://registry.hub.docker.com', 'dockerhub_id') {customImage.push()}
        }

      }
    }

  }
  environment {
    registry = 'mariusz67/cicd_pipeline'
    registryCredential = 'dockerhub_id'
  }
}