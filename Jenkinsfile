pipeline {
    agent any

    triggers {
        cron('H/2 * * * *')
        pollSCM('H/1 * * * *')
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/dishamaiti/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }

        stage('Echo Build Status') {
            steps {
                echo "Build completed successfully!"
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '*.txt', fingerprint: true
            }
        }
    }
}
