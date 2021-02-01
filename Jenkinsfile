pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    tools{
       Nodejs 'Nodejs'
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
