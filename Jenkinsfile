pipeline {
  agent { label 'linux' }
  tools {
    maven 'maven-3.6-'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/log4jenkins/myProject.git'
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
