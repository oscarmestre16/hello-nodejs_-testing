pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    tools{
       nodejs 'NodeJS'
    }
    stages {
       
        stage('Build') {
            steps {                
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
                sh 'npm run ci-test'
            }
            post{
                always{
                    junit ''
                    step([
                        $class:'CloverPublisher',
                        cloverReportDir: 'build/coverage',
                        cloverReportFileName: 'build/logs/clover.xml'
                    )]
                }
            }
        }
    }
}
