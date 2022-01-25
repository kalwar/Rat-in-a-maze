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
                sh 'sudo ./scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh 'sudo ./scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'sudo ./scripts/kill.sh'
            }
        }
    }
}
