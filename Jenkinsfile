pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    //tools  
    stages {
       
        stage('Build') {
            steps {                
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'cpm test'
                sh 'npm ci-test'
        }
