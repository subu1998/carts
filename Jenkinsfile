pipeline {
  agent {
    docker {
      image 'schoolofdevops/carts-maven'
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
}