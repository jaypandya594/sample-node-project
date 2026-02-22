pipeline {
    // Run this pipeline on any available server
    agent any 

    stages {
        
        stage('Fetch Code') {
            steps {
                git branch: 'dev', url: 'https://github.com/jaypandya594/sample-node-project.git'
            }
        }

    
        stage('Build Image') {
            steps {
                sh 'docker build -t my-node-app .'
            }
        }

      
        stage('Run App') {
            steps {
              
                sh 'docker rm -f my-app-container || true'
                sh 'docker run -d -p 8081:3000 --name my-app-container my-node-app'
            }
        }
    }
}
