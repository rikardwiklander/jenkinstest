pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Run and test .sh-files') {
          steps {
            git 'https://github.com/rikardwiklander/jenkinstest'
            sh './touch_test.sh'
            sh './error_file.sh'
          }
        }
        stage('Cat test') {
          steps {
            sh '/cat /tmp/test.txt'
          }
        }
        stage('See if file exists') {
          steps {
            fileExists '/tmp/test.txt'
          }
        }
      }
    }
  }
}