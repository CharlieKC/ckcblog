pipeline {
  agent any
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/CharlieKC/ckcblog.git', credentialsId: 'git', poll: true)
      }
    }

    stage('npm') {
      steps {
        sh 'npm install'
      }
    }

    stage('gatsby build') {
      steps {
        sh 'gatsby build'
      }
    }

    stage('gatsby serve') {
      steps {
        sh 'gatsby serve'
      }
    }

  }
}