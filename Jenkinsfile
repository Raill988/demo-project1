pipeline {
  agent any
  stages {
    stage('log Tool Version') {
      parallel {
        stage('log Tool Version') {
          steps {
            sh '''mvn --version
git --version
java -version'''
          }
        }

        stage('Check for POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('post Build Step') {
      steps {
        writeFile(file: 'status.txt', text: 'hey it works')
      }
    }

  }
}
