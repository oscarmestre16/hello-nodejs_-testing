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
                    step([$class: "TapPublisher", testResults: "test.tap"])
                     step([
                        $class: 'CloverPublisher',
                        cloverReportDir: '/var/coverage/reports/',
                        cloverReportFileName: 'coverage.xml',
                        healthyTarget: [methodCoverage: 70, conditionalCoverage: 80, statementCoverage: 80],
                        unhealthyTarget: [methodCoverage: 50, conditionalCoverage: 50, statementCoverage: 50],
                        failingTarget: [methodCoverage: 0, conditionalCoverage: 0, statementCoverage: 0]
                    ])
                }
            }
        }
    }
}
