pipeline {
    agent any
    stages {
        
        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
            }
        }
        stage('Checkout SCM') {
            steps {
                git url 'https://github.com/jiaxuan7/JenkinsDependencyCheckTest'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
