pipeline {
  agent any
  stages {
    stage('staging') {
      steps {
        echo 'hello'
        cleanWs(cleanWhenSuccess: true, skipWhenFailed: true)
      }
    }

    stage('build') {
      steps {
        withAnt(installation: 'pub.rar', jdk: '1.5') {
          sleep 30
        }

        pwd(tmp: true)
      }
    }

    stage('deploy') {
      steps {
        waitUntil()
        fileExists 'jenkinsfile'
      }
    }

  }
}