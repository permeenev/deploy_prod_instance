pipeline {
    agent any
    stages {
        stage('test') {
            tools{
                terraform
            }
            steps {
                // Get some code from a GitHub repository
                sh " git clone 'https://github.com/permeenev/deploy_prod_instance.git'"
                sh "ls -la"
                sh "terraform --version"
            }

        }
    }
}
