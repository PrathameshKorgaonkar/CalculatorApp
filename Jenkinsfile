pipeline {
    agent any 
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
