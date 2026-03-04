pipeline{
    agent any
    stages{
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage ('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage ('npm test') {
            steps {
                sh 'npm test'
            }
        }
        stage ('build') {
            steps {
                sh 'echo "Build stage completed..."'
            }
        }
        stage ('archive') {
            steps {
                archiveArtifacts artifacts: '**/*', fingerprint: true
            }
        }
    }
}