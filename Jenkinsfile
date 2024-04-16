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
                    def lastLog = lastBuild.getLogText()
                    def currentLog = currentBuild.getLogText()
                    
                    if (!lastLog.equals(currentLog)) {
                        echo "Build logs are different:"
                        def diff = diff(lastLog, currentLog)
                        echo "Difference:"
                        echo diff
                    } else {
                        echo "Build logs are identical."
                    }
                } else {
                    echo "No previous build to compare with."
                }
            }
        }
    }
    
    def diff(String oldStr, String newStr) {
        return newStr.replace(oldStr, "")
    }
}
