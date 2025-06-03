pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        docker { image 'maven:3.8.1-adoptopenjdk-11' }
      }
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Run Java App') {
      agent {
        docker { image 'openjdk:11-jre-slim' }
      }
      steps {
        sh 'java -cp target/classes com.example.App'
      }
    }
  }
}

