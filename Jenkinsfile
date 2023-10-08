pipeline {
    agent { label 'ubuntu' }

    stages {
        stage('Verify tooling') {
            steps {
                script {
                    sh 'docker version'
                    sh 'docker-compose version'
                }
            }
        }
        stage('Prune Docker Data') {
            steps {
                script {
                    sh 'docker system prune --all --volumes --force'
                }
            }
        }
        stage('Start container') {
            steps {
                sh 'docker-compose up --detach'
                sh 'docker-compose ps -a'
            }
        }
    }
}
