pipeline {
    agent any
    stages {
        stage('Download-Code-GIT') {
            steps {
                echo "Download code from git"
                git branch: 'main', url: 'https://github.com/Shrujal82/maven-jenkins7.git'
            }
        }
        stage('Build') {
            steps {
        sh '''docker build -t shrujal/tomcat:v${BUILD_NUMBER} .
            docker tag shrujal/tomcat:v${BUILD_NUMBER} devopstechlab/tomcat:latest 
            docker push shrujal/tomcat:v${BUILD_NUMBER}
            docker push shrujal/tomcat:latest '''
            }
        }
    }
}
