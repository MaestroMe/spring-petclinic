pipeline {
    agent any

    stages {
        stage('Build') { 
            steps {
                bat 'mvn -B -DskipTests clean package' 
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
        stage('Archive') {
            steps {
                archiveArtifacts 'target/**/*.jar'
            }        
        }
        stage('Deliver') { 
            steps {
                echo "Ready to deploy to target machines" 
            }
        }
    }
}