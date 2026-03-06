pipeline {
    agent any

    stages {
        stage('Check out') {
            steps {
                git 'https://github.com/Ashishwayachal12/Maven_Sample_Project1.git'
                echo 'repo clone successful'
            }
        }
        stage('fileExists'){
            steps{
                fileExists '/var/lib/jenkins/workspace/Maven_Project1'
            }
        }
        stage('Maven Build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('Run Jar'){
            steps{
                 sh 'java -jar target/java-project2-2.1.jar'
            }
        }
         stage('Clean Workspace'){
            steps{
               cleanWs()
            }
        }
    }
}
