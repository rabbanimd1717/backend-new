pipeline {
    agent {
       label 'AGENT-1' 
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    environment { 
        Name = 'Rabbani'
    }

    stages {
        stage('Testing') {
            steps {
                sh """
                    echo "This is testing purpose"
                    ls -ltr
                """
            }
        }
    }   
    post {
        always{
            sh 'echo this job run always'
            deleteDir()
        }
        success {
            sh 'echo this is only job is success'
        }
        failure {
            sh 'echo this is only failure'
        }
    }
}