pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                if (isUnix()) {
                sh './gradlew clean buildImage'
                } else {
                 bat 'gradlew.bat clean build'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}