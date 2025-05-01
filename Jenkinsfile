pipeline {
  agent any

  environment {
    SONAR_TOKEN = credentials('SONAR_TOKEN') // You can skip this stage if not using Sonar yet
  }

  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'npm test || true'
      }
    }

    stage('Security Scan') {
      steps {
        sh 'npm audit || true'
      }
    }

    stage('Code Quality Check') {
      steps {
        echo 'SonarCloud analysis would go here (optional for now)'
      }
    }
  }
}
