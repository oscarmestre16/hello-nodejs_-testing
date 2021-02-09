pipeline {
    agent any
   
    options {
        ansiColor('xterm')
    }
    stages {       
        stage('Security') {
            steps {
                sh 'trivy filesystem -f json -o trivy-fs.json .'
                sh 'trivy image -f json -o trivy-image.json hello-brunch'
                recordIssues enabledForFailure: true, aggregatingResults:true, tool: trivy(pattern: 'trivy-*.json')
            }
        }
    }
}
