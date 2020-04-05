pipeline {
    agent any 
    
    tools {
      maven 'Maven 3.5.4'
    }
    
    stages {
        stage('Build') { 
            steps {
                echo 'Building...'
                sh 'mvn clean compile'
            }
        }
        stage('Test') { 
            steps {
                echo 'Testing...'
                sh 'mvn test'
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Packaging'
                sh 'mvn -DskipTests package'
                archiveArtifacts artifacts: '**/target/*.jar*', fingerprint: true
            }
        }
    }
}
