pipeline {
  agent any
  stages {
    stage('Check for POM') {
      parallel {
        stage('Check for POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

        stage('tst') {
          steps {
            pwd(tmp: true)
          }
        }

      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('Post Build Steps') {
      steps {
        writeFile(file: 'status.txt', text: 'Hey it worked!!!')
      }
    }

  }
}