pipeline {
    agent any

   tools {
    jdk 'jdk_21'
    maven 'maven 3.9.9'
}


    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/JamieJay1/docker-spring-boot-java-web-service.git', branch: 'master'
            }
        }

        stage('Build Phase') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test Phase') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
