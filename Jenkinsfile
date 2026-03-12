pipeline {
    agent { label "kali" }

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
                sh ''' 
                    mv target/*.jar app.jar
                     java -jar app.jar'''
            }
        }
         stage('Clean Workspace'){
            steps{
               cleanWs()
            }
        }
    }
}
