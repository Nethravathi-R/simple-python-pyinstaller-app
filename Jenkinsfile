pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 --version'
            }
        }
    
      
        stage('Test') { 
            steps {
                sh 'This is Test stage' 
            }
            post {
                always {
                    junit 'test-reports/results.xml' 
                }
            }
        }
    }
}
