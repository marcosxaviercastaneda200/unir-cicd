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
               echo 'results. ddd'
            }
        }
    }
    post {
        always {
           echo 'Post action'
        }
    }
}