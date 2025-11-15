pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/asit6371/git-cache-maintenance-in-jenkins.git'
            }
        }

        stage('Disk Space Before Cleanup') {
            steps {
                echo '📊 Disk space BEFORE cleanup'
                bat 'powershell -Command "Get-PSDrive C | Select-Object Used,Free,Name"'
            }
        }

        stage('Git Cache Maintenance') {
            steps {
                echo '🧹 Running Git Cache Cleanup...'
                bat 'git gc --prune=now --aggressive'
                echo '✅ Cleanup completed successfully.'
            }
        }

        stage('Disk Space After Cleanup') {
            steps {
                echo '📊 Disk space AFTER cleanup'
                bat 'powershell -Command "Get-PSDrive C | Select-Object Used,Free,Name"'
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
