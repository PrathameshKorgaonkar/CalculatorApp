pipeline {
    agent any 
    stages {
        stage('build') {
            steps {
                sh 'g++ main.cpp'
                sh './a.out'
            }
        }
    }
    
}
