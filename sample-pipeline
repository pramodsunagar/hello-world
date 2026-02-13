pipeline {
    agent any

    tools {
        jdk 'JDK17'          // Name must match Jenkins tool config
        maven 'Maven3'       // Name must match Jenkins tool config
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'WAR file generated successfully.'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
