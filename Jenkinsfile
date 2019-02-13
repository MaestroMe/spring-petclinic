pipeline {
    agent any

    stages {
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.5') {
                        bat 'mvn clean package sonar:sonar'
                    }
                }
            }
        }             
        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Deliver') { 
            steps {
                echo "Ready to deploy to target machines" 
            }
        }
   
    }
}