pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Yashaswiiii8/MyGradleApp.git'
            }
        }

        stage('Build') {
            steps {
               sh './gradlew build -Dorg.gradle.java.home=/opt/jdk17'
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
