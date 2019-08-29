pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn clean install -DskipTests'
            }
        }
        stage('Test') {
            steps {
            echo 'Running test cases....'
               bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                bat 'mvn spring-boot:run'
            }
        }
    }
}
