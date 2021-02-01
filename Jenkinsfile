pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    tools{
        Node15.7
    }
    stages {
       
        stage('Build') {
            steps {                
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
                sh 'npm ci-test'
            }
        }
    }
}
