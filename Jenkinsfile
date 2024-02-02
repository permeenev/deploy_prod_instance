pipeline {
    agent any
    tools{
        terraform "terraform1.7.1"
    }
    stages {
        stage('test') {

            steps {
                // Get some code from a GitHub repository
                sh "pwd"
                sh "ls -la"
                sh "terraform --version"
            }

        }
    }
}
