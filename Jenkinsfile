pipeline {
    agent any
    tools{
     jdk 'Java17'
    }
    stages {
        stage('Clean workspace and Navigate to the folder'){
            steps{
                cleanWs()
                bat 'copy C:\\\\Users\\\\Lenovo\\\\Desktop\\\\JenkinsDemo "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\SCM pipeline java code"'
            }
        }
    stage('Build') {
            steps {
                bat 'javac Pattern.java'
            }
        }
        stage('Jar') {
            steps {
                bat 'jar cfe myJar.jar Pattern Pattern.class'
            }
        }
        stage('Run') {
            steps {
                bat 'java -jar myJar.jar'
            }
        }
        stage('Artifact'){
            steps{
                archiveArtifacts artifacts: '*.jar', followSymlinks: false
            }
        }
    }
}
       
