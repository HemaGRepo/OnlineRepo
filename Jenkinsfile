pipeline {
  agent any
  stages {
    stage('BuildTask') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the code...'
          }
        }
        stage('Compile') {
          steps {
            bat 'javac HelloWorld.java'
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Testing the code...'
      }
    }
    stage('Execution') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deployed the code..'
          }
        }
        stage('Execute') {
          steps {
            bat 'java HelloWorld'
          }
        }
      }
    }
    stage('Report') {
      steps {
        echo 'Completed'
      }
    }
  }
}