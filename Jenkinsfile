pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                'mvn clean package'
            }
        }
        stage('Test') { 
            steps {
                'mvn test' 
            }
        }
    }
}