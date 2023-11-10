pipeline {
    agent
    stages {
        stage('Build') {
            steps {
                echo 'Building stage!'
            }
        }
        stage('Unit tests') {
            steps {
               echo 'results'
            }
        }
    }
    post {
        always {
           echo 'Post action'
        }
    }
}