pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building project..."
                sh 'chmod +x gradlew'
                sh './gradlew clean build'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running app..."
                sh './gradlew run'
            }
        }

        stage('Custom Task (Guava)') {
            steps {
                echo "Running custom task..."
                sh './gradlew guavaTask'
            }
        }

        stage('Print Dependencies') {
            steps {
                echo "Printing dependencies..."
                sh './gradlew dependencies'
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
