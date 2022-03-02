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

        stage('Test Log') {
          steps {
            environment {
    DockerDirPath = 'C:\\Program Files\\Docker\\Docker'
    }
            writeFile(file: 'LogFile.txt', text: 'This is an JenKins war file path ${JenkisWarPath} and This is Docker Directory Path ${DockerDirPath} ')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do You want to Deploy??', id: 'OK')
            echo 'To Deploy the application server'
          }
        }

        stage('TestLog') {
          steps {
            archiveArtifacts 'LogFile.txt'
          }
        }

      }
    }

  }
  environment {
    JenkisWarPath = 'C:\\Jenkins_war\\Jenkins'
  }
}