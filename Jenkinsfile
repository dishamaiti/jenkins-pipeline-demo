pipeline {
    agent any

    tools {
        maven 'Maven_HOME'
    }

    triggers {
        pollSCM('H/2 * * * *')   // Poll every 2 minutes
        cron('H/5 * * * *')      // Build every 5 minutes
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/dishamaiti/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Echo Build Status') {
            steps {
                echo "Build completed successfully!"
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}

             
