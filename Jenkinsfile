pipeline {
  agent any
  stages {
    stage('GetSources') {
      steps {
        git 'https://github.com/ecocquerez/TestDivers.git'
      }
    }
  }
  environment {
    stage = 'premier'
  }
}