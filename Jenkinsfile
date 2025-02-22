pipeline {
    agent any

    environment {
        VIRTUAL_ENV = "${WORKSPACE}/venv"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://your-git-repo-url.git'
            }
        }

        stage('Setup Python Environment') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                sh '. venv/bin/activate && python app.py &'
            }
        }

        stage('Test Application') {
            steps {
                sh '. venv/bin/activate && pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment Step - Customize as per your setup'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
