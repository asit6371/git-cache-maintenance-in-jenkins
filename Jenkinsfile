pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/asit6371/git-cache-maintenance-in-jenkins.git'
            }
        }
        stage('Git Cache Maintenance') {
            steps {
                echo 'Running Git Cache Cleanup...'
                bat 'git gc --prune=now --aggressive'
                echo 'Cleanup completed successfully.'
            }
        }
    }
    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
