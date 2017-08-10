pipeline {
    agent none 
    stages {
        stage('Example Build') {
            agent { docker 'maven:3-alpine' } 
            steps {
                echo 'Hello, Maven'
                sh 'printenv'
                sh 'ls'
                sh 'mvn --version'
            }
        }
        stage('Sanity check') {
            agent none 
            steps {
                input "Does the staging environment look ok?"
            }
        }
        stage('Example Test') {
            agent { docker 'openjdk:8-jre' } 
            steps {
                echo 'Hello, JDK'
                sh 'printenv'
                sh 'ls'
                sh 'java -version'
            }
        }
    }
}
