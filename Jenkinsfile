pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    stages {
       
        stage('Build') {
            steps {                
                sh 'yarn'
            }
        }
        stage('Test') {
            steps {
                sh 'yarn test'
                sh 'yarn ci-test'
        }
