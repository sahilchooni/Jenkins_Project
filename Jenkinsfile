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
          environment {
            DockerDirPath='C:\\Program Files\\Docker\\Docker'
          }
          steps {
          
            writeFile(file: 'LogFile.txt', text: "This is an JenKins war file path ${JenkisWarPath} and This is Docker Directory Path ${DockerDirPath} ")
          }
        }

      }
    }

    stage('Deploy'){
    when {
         branch 'main'
    }
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