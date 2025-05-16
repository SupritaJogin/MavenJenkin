pipeline {
    agent any

   tools {
        jdk 'jdk24'
        maven 'Maven'
    }


    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Hemavathipcse/GradleJenkinsPipeline.git'
            }
        }

        stage('Build') {
            steps {
                bat 'gradle build'
            }
        }

        stage('Test') {
            steps {
                bat 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                bat 'gradle run'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
