pipeline {
  agent any
  stages {
    stage('fetch code') {
      steps {
        git(url: 'https://github.com/CharlieKC/ckcblog.git', poll: true)
      }
    }

    stage('ls files') {
      parallel {
        stage('ls files') {
          steps {
            sh 'ls -a;'
          }
        }

        stage('') {
          steps {
            retry(count: 1) {
              sh 'killall node'
            }

          }
        }

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