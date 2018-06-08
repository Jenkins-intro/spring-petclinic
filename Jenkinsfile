pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'mvn verify'
          }
        }
        stage('parallel build') {
          steps {
            powershell 'mvn verify'
          }
        }
      }
    }
    stage('Test') {
      steps {
        findbugs(canComputeNew: true)
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }
  }
}