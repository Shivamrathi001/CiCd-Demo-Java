pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo "hello Build"
      }
    }
    stage('deploy') {
      steps {
        withAWS(region:'us-east-1',credentials:'aws') {
          sh 'echo "Uploading content with AWS creds"'
          s3Upload(file:'./target/demo-0.0.1-SNAPSHOT.jar', bucket:'jenkins-test-javaupload')
//           sh '
//           aws s3 cp ./target/demo-0.0.1-SNAPSHOT.jar s3://jenkins-test-javaupload/demo-0.0.1-SNAPSHOT.jar '
        }
      }
    }
  }
}
