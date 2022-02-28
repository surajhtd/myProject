pipeline {
  agent { label 'master' }
  tools {
    maven 'maven384'
  }
  stages {
    stage('checkout') {
      steps {
        git 'git@github.com:surajhtd/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
