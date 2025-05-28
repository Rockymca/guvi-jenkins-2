pipeline {
    agent any

    stages {
        stage('Run Script') {
            steps {
                sh 'chmod +x sample.sh'
                sh './sample.sh'
            }
        }
    }

    post {
        success {
            emailext(
                subject: 'Build Successful: ${JOB_NAME} #${BUILD_NUMBER}',
                body: 'Build finished successfully.\n\nCheck console: ${BUILD_URL}',
                to: 'rocky5030@gmail.com'
            )
        }
        failure {
            emailext(
                subject: 'Build Failed: ${JOB_NAME} #${BUILD_NUMBER}',
                body: 'Build failed.\n\nCheck console: ${BUILD_URL}',
                to: 'rocky5030@gmail.com'
            )
        }
    }
}
