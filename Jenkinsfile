pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        echo 'echo \'Building application...\''
        sleep(time: 10, unit: 'SECONDS')
        echo 'echo \'Running tests...\''
      }
    }

  }
  environment {
    APP_NAME = 'hello_world'
  }
}