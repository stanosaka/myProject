pipeline {
  agent any
  tools {
    maven 'Default Maven'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/stanosaka/myProject.git'
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
