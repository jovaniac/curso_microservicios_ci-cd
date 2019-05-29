pipeline {
 
    environment {
        CI = 'true'
    }
    stages {

         stage('Descargando Codigo') {
            checkout scm
         }

        stage('Compilando, Build e imagen docker') {
           if (isUnix()) {
                sh './gradlew clean buildImage'
           } else {
          bat 'gradlew.bat clean build'
           }
        }
     
        stage('Deliver') {
            steps {
               echo 'publicando codigo...'
            }
        }
    }
}