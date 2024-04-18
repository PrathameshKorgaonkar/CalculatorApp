pipeline {
    agent Linux-Node-v1
    stages {
        stage('build') {
            steps {
                sh 'g++ main.cpp'
            }
        }
        stage('run') {
            steps {
                sh './a.out'
            }
        }
    }
    
}
