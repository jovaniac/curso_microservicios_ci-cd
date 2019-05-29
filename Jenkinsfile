node {


    env.DOCKER_API_VERSION="1.23"
    sh "git rev-parse --short HEAD > commit-id"
    tag = readFile('commit-id').replace("\n", "").replace("\r", "")
    appName = "cliente"
    registryHost = "http://10.51.33.59:5000/"
    //imageName = "${appName}:${tag}"
    imageName = "jovaniac/servicio-cliente:0.0.1-SNAPSHOT"
    env.BUILDIMG=imageName
  
   stage('Descargando Codigo') {
    checkout scm
   }
  
  stage('Gradle Build') {
      if (isUnix()) {
          sh './gradle clean buildImage'
      } else {
          bat 'gradlew.bat clean build'
      }
  }
  
   stage "Build Image"
          echo 'Building..'
          sh "docker build -t ${imageName} build/libs/"
    echo 'End Building..'

    stage('Deploy docker'){
         echo 'Deploy..'
    }
    
    }
