pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t my-devops-site .'
            }
        }
        stage('Deploy Container') {
            steps {
                // Stop old version if it exists, then run the new one
                sh 'docker rm -f local-web-server || true'
                sh 'docker run -d -p 8888:80 --name local-web-server my-devops-site'
            }
        }
    }
}

