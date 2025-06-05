pipeline {
    agent any

    tools {
        maven 'Maven3'        // use exact name from Jenkins config
        jdk 'OpenJDK11'       // use exact name from Jenkins config
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/FaizShaikh27/JenkinsPipeline.git'
            }
        }

        stage('Build') {
            steps {
                dir('demo') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                dir('demo') {
                    sh 'mvn test'
                }
            }
        }
    }

    post {
        success {
            echo 'Build completed!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
