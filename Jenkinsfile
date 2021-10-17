pipeline {
    agent any
    stages {
        stage ('Checkout') {
            steps {
                script {
                    git([url: 'https://github.com/sudheermanubolu/5180_week6.git', branch: 'main', credentialsId: 'github-jenkins'])
                }
            }
        }
        stage('Install Docker') {
            steps{
                sh 'echo "all build steps here"'
            }
        }
        stage('Download Kubectl') {
            steps{
                sh 'curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"'
                sh 'chmod +x kubectl' 
            }
        }
        stage('start load test') {
            steps{
                sh "./start_test.sh Jenkins_test.jmx"
            }
        }
        stage('Deployment') {
            steps{
                sh 'echo "Deployment steps here"'
            }
        }
    }
}