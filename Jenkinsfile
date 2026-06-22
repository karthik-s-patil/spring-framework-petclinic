pipeline {
    agent any

    tools {
        jdk 'jdk21'
        maven 'maven3'
    }

    environment {
        SCANNER_HOME= tool 'sonar-scanner'
    }
    stages {
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Sonar-Scanner') {
            steps {
                withSonarQubeEnv('sonar-scanner') {
                   sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Petclinic -Dsonar.projectKey=Petclinic -Dsonar.java.binaries=. '''
                }
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                withMaven(globalMavenSettingsConfig: 'mvn-config', jdk: 'jdk21', maven: 'maven3', traceability: true) {
                     sh 'mvn deploy'
                }
            }
        }
        stage('Tomcat-Deploy') {
            steps {
                script {
                 sh 'scp target/petclinic.war ubuntu@13.126.252.94:/home/ubuntu/apache-tomcat-10.1.55/webapps/'
                }
            }
        }
    }
}
