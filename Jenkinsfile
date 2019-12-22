pipeline {
  agent any
  stages {
    stage('fetch code') {
      steps {
        git 'https://github.com/CharlieKC/ckcblog.git'
      }
    }

    stage('ls files') {
      steps {
        sh 'ls -a;'
      }
    }

    stage('build') {
      steps {
        sh '''npm install;
gatsby build;'''
      }
    }

  }
}