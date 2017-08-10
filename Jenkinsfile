pipeline {
    agent none 
    stages {
        stage('Prebuild') {
            agent none
            steps {
                sh 'git status'
            }
        }
        stage('Example Build') {
            agent { docker 'maven:3-alpine' } 
            steps {
                echo 'Hello, Maven'
                sh 'printenv'
                sh 'mvn --version'
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
