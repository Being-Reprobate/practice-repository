pipeline {
    agent {
        docker { image 'node:20.15.0-alpine3.20' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'nde --version'
            }
        }
    }
    post{
        failure{
            mail to: 'srujalprajapti04@gmail.com',
            subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
            body:"Something is wrong in the build id : ${env.BUILD_URL}"
        }
    }
}
