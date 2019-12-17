pipeline {
  agent any

  stages {
    stage('Count') {
      steps {
        sh 'echo ${BUILD_NUMBER}'
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
  }
}
