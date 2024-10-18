pipeline {
    agent any // Use any available agent to run the job

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the SCM (GitHub in this case)
                git branch: '2.1-master', url: 'https://github.com/sravan513/thymeleafexamples-petclinic.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven to build the project
                sh 'mvn clean install'
            }
        }
    post {
        always {
            // Always clean up workspace after the build
            cleanWs()
        }

        success {
            // Notify on success (optional)
            echo 'Build succeeded!'
        }

        failure {
            // Notify on failure (optional)
            echo 'Build failed!'
        }
    }
}
