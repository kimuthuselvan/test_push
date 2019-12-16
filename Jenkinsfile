pipeline {
  agent any

  stages {
    stage('Count') {
      steps {
        sh 'echo ${BUILD_NUMBER}'
	sh 'echo ${BUILD_NUMBER} > mytext.txt'
      }
    }
  }
}
