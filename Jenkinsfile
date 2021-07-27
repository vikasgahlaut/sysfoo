pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.war'
      }
    }

  }
  
  post
  {
    always{
      echo 'This pipeline is completed..'
    }
  } 
    
  tools {
    maven 'Maven 3.6.3'
  }
}
