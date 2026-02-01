pipeline {
    agent { label 'docker-host' }

    stages {
        stage('Info') {
            steps {
                echo "Running pipeline for branch: ${env.BRANCH_NAME}"
            }
        }
    }
}

