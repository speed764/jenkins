pipeline {
    agent any
    
    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
                checkout scm
            }
        }

        stage('Test Code') {
            steps {
                echo "Running tests..."
                sh 'mvn test'
            }
        }

        stage('Build Application') {
            steps {
                echo "Building application..."
                sh 'mvn clean package'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo "Archiving artifacts..."
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed. Check logs."
        }
        always {
            echo "🔄 Pipeline finished."
        }
    }
}
