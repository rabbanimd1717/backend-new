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
        def appVersion = ''
    }

    stages {
        stage('read the json version') {
            steps {
                script{
                    def packageJson = readJSON file: 'dir/package.json'
                    appVersion = packageJson.version
                    echo "application version: $appVersion"

                }
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