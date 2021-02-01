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
                sh 'yarn run test'
                sh 'yarn run ci-test'
            }
            post{
                archive 'build/libs/*.jar'
            }
        }
    }
}
