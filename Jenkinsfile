pipeline {
    agent any
    stages {

        stage('Checkout SCM') {
            steps {
                git url: 'https://github.com/jiaxuan7/JenkinsDependencyCheckTest'
            }
        }
        stage('OWASP DependencyCheck') {
                    steps {
                        dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
                    }
                }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
