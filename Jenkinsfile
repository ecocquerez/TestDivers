pipeline {
  agent any
  stages {
    stage('GetSources') {
      steps {
        git 'https://github.com/ecocquerez/TestDivers.git'
      }
    }
    stage('Informations') {
      steps {
        echo 'Running on server : ${env.NODE_NAME}'
        echo 'Numero de build : ${env.BUILD_NUMBER}'
        echo 'Nom de la branche : ${env.BRANCH_NAME}'
        echo 'Espace de travail : ${env.WORKSPACE}'
      }
    }
    stage('Restore Nugget') {
      steps {
        powershell(returnStatus: true, script: '..\\\\Build\\\\RestoreNugget.ps1 -branch ${env.BRANCH_NAME}')
      }
    }
    stage('FxCop') {
      steps {
        tool 'FxCop MSV14'
      }
    }
  }
  environment {
    stage = 'premier'
  }
}