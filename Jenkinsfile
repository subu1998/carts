pipeline {
  agent {
    docker {
      image 'maven:3-openjdk-11'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        echo 'Packaging....'
        sh 'mvn -DskipTests package'
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'maven 3.9.1'
  }
}