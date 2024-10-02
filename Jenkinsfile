pipeline {
    agent any
    tools {
        nodejs "nodejs18"
    }

    triggers{
        githubPush()
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }
    post {
        always {
            echo 'Pipeline finalizado. Limpieza del entorno.'
        }
        success {
            echo 'El pipeline ha finalizado correctamente.'
        }
        failure {
            echo 'El pipeline ha fallado.'
        }
    }
}
