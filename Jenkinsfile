pipeline {
    agent any

    tools {
        maven 'Maven'
    }
    
    stages {
        stage('GitHub') {
            steps {
               git credentialsId: 'hello_sheik', url: 'https://github.com/sheik-03/java-helloworld.git' 
            }
        }
        stage('build') {
            steps{
                sh 'mvn --version'
                echo 'maven version successfully installed'
            }
        }
        stage('test') {
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('deploy') {
            steps {
                sh 'mvn test'
            }
        }
        stage('runthe helloworld') {
            steps {
                sh 'mvn exec:java'
            }
        }
        post {
            success {
                sh 'echo java successfully run'
            }
            failure {
               sh 'echo java failure'
            }
        }
        
    }
}

