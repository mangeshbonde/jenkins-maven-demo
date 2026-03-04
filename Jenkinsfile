pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

         stage('Run Application') {
            when {
                expression { currentBuild.currentResult == 'SUCCESS' }
            }
            steps {
                sh 'nohup java -jar target/*.jar > app.log 2>&1 &'
            }
        }
    options {
        timeout(time: 5, unit: 'MINUTES')
    }

    post {
        success {
            echo '✅ Build Successful - Pipeline Completed'
        }
        failure {
            echo '❌ Build Failed'
        }
    }
}
