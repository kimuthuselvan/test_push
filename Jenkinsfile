pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        sh 'git checkout master'
		sh 'git pull'
      }
    }
    stage('Count') {
      steps {
        sh 'echo ${BUILD_NUMBER}'
        sh 'echo Jenkinsfile'
        sh 'echo ${BUILD_NUMBER} > mytext.txt'
      }
    }
    stage('Commit') {
      steps {
        sh 'cat mytext.txt'
        sh 'ls -lh'
        sh 'git commit -m "Jenkins commit after build" mytext.txt'
        sh 'git push --all --verbose'
      }
    }
    stage ('Downstream1') {
      steps {
        build job: 'Pipeline_A'
      }
    }
  }
}
