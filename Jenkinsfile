pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
               git branch: 'main', url: 'https://github.com/srinfotechbatch3/spring-petclinic.git'
            }
        }
        
         stage('Build') {
            steps {
               bat 'mvn clean install'
            }
        }
         stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
         stage('Test Reports') {
            steps {
               junit 'target/surefire-reports/*.xml'
            }
        }
         stage('Generated Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        
         stage('Deploy to Server') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
