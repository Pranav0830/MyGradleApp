pipeline {
    agent any

    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Pranav0830/MyGradleApp.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'  // Run Gradle build
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                sh './gradlew run'  // Start the application
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

