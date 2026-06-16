pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Repository cloned successfully'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t techfest-website .'
            }
        }

        stage('Deploy Container') {
            steps {
                bat 'docker rm -f techfest-container || exit 0'
                bat 'docker run -d -p 8080:80 --name techfest-container techfest-website'
            }
        }
    }
}