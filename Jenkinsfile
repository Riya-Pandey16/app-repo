pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Riya-Pandey16/app-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Deploy using Ansible') {
            steps {
                sh '''
                ansible-playbook -i ../ansible-repo/inventory \
                ../ansible-repo/deploy_app.yml
                '''
            }
        }
    }
}

