pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn -B -DskipTests clean install' 
                archiveArtifacts 'target/**.jar'
            }
        }
        stage('Test') {
            steps {
            echo 'Running test cases....'
               sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'mvn spring-boot:run'
            }
        }
    }
}
