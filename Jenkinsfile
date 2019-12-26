pipeline {
  agent any
  stages {
    stage('fetch code') {
      parallel {
        stage('fetch code') {
          steps {
            git(url: 'https://github.com/CharlieKC/ckcblog.git', poll: true)
          }
        }

        stage('kill running server') {
          steps {
            sh '''kill -9 $(lsof -t -i:3000)
'''
          }
        }

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
        sh '''gatsby serve -p 3000 &;
sleep 3;
disown;'''
      }
    }

  }
}