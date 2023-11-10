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
               echo 'results again'
            }
        }
    }
    post {
        always {
           echo 'Post action'
        }
    }
}