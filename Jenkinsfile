pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    stages {

        stage('Build & Test') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive Artifact') {
            when {
                expression { currentBuild.currentResult == 'SUCCESS' }
            }
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful - JAR Archived'
        }
        failure {
            echo '❌ Build Failed'
        }
    }
}
