pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'Hello World!'
        fileExists 'index.jsp'
        sh 'mvn -B -DskipTests clean package'
        archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
      }
    }

  }
}
