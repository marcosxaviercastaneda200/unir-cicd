pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building stage!'
            }
        }
        stage('Unit tests') {
            steps {
               echo 'results.d'
            }
        }
    }
    post {
        always {
           echo 'Post action'
        }
    }
}