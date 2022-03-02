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
            echo "To Get The path of JenkinsWar ${JenkisWarPath}"
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
  environment {
    JenkisWarPath = 'C:\\Jenkins_war\\Jenkins'
  }
}