pipeline {
    agent any
    
    tools {nodejs "node"}
    
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh "chmod +x -R ./scripts/"
                sh './scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh "chmod +x -R ./scripts/"
                sh './scripts/kill.sh'
            }
        }
    }
}
