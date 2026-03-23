pipeline {
    agent any

    tools {
        jdk 'jdk17'
        gradle 'gradle'
        
    }

    environment {
        GRADLE_OPTS = "-Dorg.gradle.daemon=false"
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
                git 'https://github.com/aaradhya177/hemawatimaamgradle.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                sh 'chmod +x gradlew'
                sh './gradlew clean build'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running application..."
                sh './gradlew run'
            }
        }

        stage('Custom Task (Guava)') {
            steps {
                echo "Running custom Gradle task..."
                sh './gradlew guavaTask'
            }
        }

        stage('Print Dependencies') {
            steps {
                echo "Printing dependencies..."
                sh './gradlew printDependencies'
            }
        }
    }

    post {
        success {
            echo "✅ Build Successful!"
        }
        failure {
            echo "❌ Build Failed!"
        }
    }
}
