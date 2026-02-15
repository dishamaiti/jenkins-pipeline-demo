pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/dishamaiti/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
            }
        }

        stage('Echo Build Status') {
            steps {
                echo "Build completed successfully"
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "No artifacts to archive"
            }
        }
    }
}

