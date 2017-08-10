node {
  try {
    stage('checkout') {
      checkout scm
    }
    stage('prepare') {
      sh "git clean -fdx"
    }
    stage('compile') {
      agent { docker 'openjdk:8-jre' } 
      echo "nothing to compile for hello.sh..."
      sh 'java -version'
    }
    stage('test') {
      sh "./test_hello.sh"
    }
    stage('package') {
      sh "tar -cvzf hello.tar.gz hello.sh"
    }
    stage('publish') {
      echo "uploading package..."
      sh "printenv"
    }
  } finally {
    stage('cleanup') {
      echo "doing some cleanup..."
    }
  }
}
