pipeline {
    agent { docker { image 'python:3.12.1-alpine3.19' } }
    stages {
        stage('build 2') {
            steps {
                sh 'python --version'
            }
        }
    
      
        stage('Test') { 
            steps {
                sh 'py.test --junit-xml test-reports/results.xml sources/test_calc.py' 
            }
            post {
                always {
                    junit 'test-reports/results.xml' 
                }
            }
        }
    }
}
