pipeline {
    agent any
    stages {
        stage('Install NodeJS') {
            steps {
                sh 'sudo apt-get install -y nodejs'
                sh 'sudo apt-get install -y npm'
                sh 'npm install'
            }
        }
        stage('git clone') {
            steps {
                sh "mkdir nextjs"
                sh "cd nextjs"
                sh "git clone https://github.com/sanyam40/CICD-NextJs"
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
