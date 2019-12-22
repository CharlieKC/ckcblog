pipeline {
  agent any
  stages {
    stage('fetch code') {
      parallel {
        stage('fetch code') {
          steps {
            git 'https://github.com/CharlieKC/ckcblog.git'
          }
        }

        stage('install node and gatsby') {
          steps {
            sh 'npm -i -g gatsby-cli'
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
        sh 'gatsby build'
      }
    }

  }
}