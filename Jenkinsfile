pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    stages {       
        stage('Security') {
            steps {
                sh 'trivy filesystem -f json -o trivy-fs.json .'                
            }
            post {
                always {
                    recordIssues enabledForFailure: true, tool: trivy(pattern: '*.json')
                }
            }

        }

    }
}
