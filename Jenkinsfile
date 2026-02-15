pipeline {
    agent any

    triggers {
        cron('H/5 * * * *')
        pollSCM('H/2 * * * *')
    }

    stages {

        stage('Build') {
            steps {
                checkout scm
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

    

