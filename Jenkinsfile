pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'This is to Build the Application'
          }
        }

        stage('Test') {
          steps {
            echo 'To Test the Application server'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'To Deploy the application server'
      }
    }

  }
}