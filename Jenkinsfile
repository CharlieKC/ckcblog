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

        stage('install environment') {
          steps {
            sh '''apt update;
apt -y upgrade; 
apt-get install curl;
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash;
nvm install 10;
nvm use 10;
npm -i -g gatsby-cli'''
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