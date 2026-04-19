pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YashasHK-06/MyGradleApp.git'
            }
        }

        stage('Setup Permissions') {
            steps {
                sh 'chmod +x gradlew'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }

        stage('Run Application') {
            steps {
                sh './gradlew run'
            }
        }
    }

    post {
        success {
            echo 'Gradle build and run successful ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
