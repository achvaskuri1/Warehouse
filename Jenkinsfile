pipeline {
    agent {
        docker {
            image 'node:16-alpine'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                    dir('backend') {
                    sh 'npm install'
                }
            }
        }
        
        stage('Test') {
            steps {
                dir('backend') {
                sh 'npm run testJenkins'
                }
            }
        }
        
        stage('Build Docker Image') {
            when{
                branch 'main'
            }
            steps{
                sh 'npm run build'
            }
        }
    }
}
