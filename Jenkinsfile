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
    
    post {
        always {
            script {
                def lastBuild = currentBuild.previousBuild
                
                if (lastBuild) {
                    def lastLog = lastBuild.rawBuild.getLog(100000) // Adjust the number of lines as needed
                    
                    echo "Previous build log:"
                    echo lastLog
                } else {
                    echo "No previous build to display."
                }
            }
        }
    }
}
