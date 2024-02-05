pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m py_compile sources/add2vals.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
        pipeline {
    agent { docker { image 'python:3.12.1-alpine3.19' } }
    stages {
        stage('build 2') {
            steps {
                sh 'python --version'
            }
        }
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
