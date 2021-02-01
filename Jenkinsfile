pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    stages {
       
        stage('Build') {
            steps {                
                sh './yarn'
            }
            post{
                archiveArtifact 'build/libs/*.jar'
            }
        }
        stage('Test') {
            steps {
                sh './yarn test'
                sh './yarn ci-test'
        }
