pipeline {
    agent any
    stages {
        stage('Build') {
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
