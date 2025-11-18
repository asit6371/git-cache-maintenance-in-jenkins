pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Dynamicpoders/git-cache-maintenance-in-jenkins'
            }
        }

        stage('Disk Space Before Cleanup') {
            steps {
                echo "📊 Disk space BEFORE cleanup"
                sh '''
                    echo "==== Disk Space ===="
                    df -h

                    echo "==== Workspace Usage ===="
                    du -sh .
                '''
            }
        }

        stage('Cleanup Workspace') {
            steps {
                echo "🧹 Cleaning up workspace"
                sh '''
                    echo "Deleting old files..."
                    rm -rf * || true
                '''
            }
        }

        stage('Disk Space After Cleanup') {
            steps {
                echo "📉 Disk space AFTER cleanup"
                sh '''
                    echo "==== Disk Space ===="
                    df -h
                '''
            }
        }
    }

    post {
        success {
            echo "✔ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed!"
        }
    }
}

