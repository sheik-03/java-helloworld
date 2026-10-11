pipeline{
    agent any

    tools{
        mvn : 'Maven'
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn --version'
                echo 'maven version successfully installed'
            }
        }
        stage('test'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('deploy'){
            steps{
                sh 'mvn test'
            }
        }
        stage('runthe helloworld'){
            steps{
                sh 'mvn exec:java'
            }
        }
        post{
            success{
                echo 'java successfully run'
            }
            failure{
                echo 'java failure'
            }
        }
        
    }
}

