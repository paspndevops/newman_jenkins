pipeline {
    agent {
        docker { 
            image 'postman/newman_ubuntu1404:2.1.2'
        }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'newman -u https://www.getpostman.com/collections/81af12a573ab17f2bc0f;'
            }
        }
    }
    post {
        success {
            echo 'The Pipeline success :)'
            sh 'docker rm newman'
        }
        failure { 
            script {
                echo 'The Pipeline failed :('
                sh 'docker rm newman'
            }
        }
    }
}
