pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    stages {       
        stage('Security') {
            steps {
                sh 'trivy filesystem --format json --output trivy-results.json .'
            }
            post {
                always {
                    recordIssues enabledForFailure: true, tool: trivy(pattern: '*.json')
                }
            }

        }

    }
}
