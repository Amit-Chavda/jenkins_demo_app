pipeline {
    agent any
    triggers { 
        pollSCM('*/1 * * * *') 
    }
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    }

    stages {
        stage('Clone') {
            steps{
                // Get some code from a GitHub repository
                git 'https://github.com/Amit-Chavda/jenkins_demo_app.git'
            }
        }
        stage('Compile') {
            steps {
                bat "javac HelloWorld.java"
            }
        }
        stage('Execute') {
            steps {
                bat "java HelloWorld"
            }
        }
    }
}
