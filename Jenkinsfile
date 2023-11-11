pipeline {
    agent any
    stages {
        stage('Source') {
            steps {
                git 'https://github.com/srayuso/unir-cicd.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building stage!'
                sh 'make build'
            }
        }
        stage('Unit tests') {
            steps {
                sh 'make test-unit'
                archiveArtifacts artifacts: 'results/*.xml'
            }
        }
    }
    post {
        always {
            junit 'results/*_result.xml'
            cleanWs()
        }
        success {
            script {
                SUBJECT = "Pipeline: ${JOB_NAME} - Build: ${env.BUILD_NUMBER} - Status: ${currentBuild.result}"
                BODY = "${currentBuild.projectName} - Build # ${env.BUILD_NUMBER} - ${currentBuild.result}: Check console output at ${env.BUILD_URL} to view the results."
                MAILTO = "mxcj@hotmail.com"
                    
            }
            mail bcc: '', body: "${BODY}", cc: '', from: '', replyTo: '', subject: "${SUBJECT}", to: "${MAILTO}"
             
        }
        failure {
            script {
                SUBJECT = "Pipeline: ${JOB_NAME} - Build: ${env.BUILD_NUMBER} - Status: ${currentBuild.result}"
                BODY = "${currentBuild.projectName} - Build # ${env.BUILD_NUMBER} - ${currentBuild.result}: Check console output at ${env.BUILD_URL} to view the results."
                MAILTO = "mxcj@hotmail.com"
                    
            }
            mail bcc: '', body: "${BODY}", cc: '', from: '', replyTo: '', subject: "${SUBJECT}", to: "${MAILTO}"
        }

    }
}
