pipeline {
    agent any
    stages {
        stage('Prepare') {
            steps {
                script {
                    sh 'rm -rf nextjs/CICD-NextJs'
                    sh 'mkdir -p nextjs/CICD-NextJs'
                }
            }
        }
        stage('git clone') {
            steps {
                dir('nextjs/CICD-NextJs') {
                    sh 'git clone https://github.com/sanyam40/CICD-NextJs .'
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                sh "docker build -t cicd-nextjs ."
            }
        }
        stage('Run Docker Container') {
            steps {
                sh "docker run -d -p 3000:3000 cicd-nextjs"
            }
        }
    }
}
