pipeline {
    agent any
    
    tools {
        maven 'Maven'
    }

    stages {

        stage('Test Code') {
            steps {
                echo "Running tests"
                sh "mvn test"
            }
        }

        stage('Build Application') {
            steps {
                echo "Building application"
                sh "mvn clean package"
            }
            post {
                success {
                    echo "Archiving artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                echo "Deploy stage"
                script {
                    // We will add deployment code here in next step
                }
            }
        }
    }
}
