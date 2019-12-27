pipeline {
  agent any
  stages {
    stage('fetch code') {
      steps {
        git(url: 'https://github.com/CharlieKC/ckcblog.git', poll: true, credentialsId: 'git')
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

    stage('serve') {
      steps {
        sh '''nohup gatsby serve -p 3000 &
echo \'server running\''''
      }
    }

  }
}