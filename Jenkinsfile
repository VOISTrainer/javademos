pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'Hello World! Build Number: ${BUILD_NUMBER}'
        fileExists 'index.jsp'
        sh 'mvn -f ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(artifacts: '**/target/*.war', fingerprint: true)
        sh '''mkdir /home/subodh/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/subodh/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}