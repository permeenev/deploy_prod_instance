pipeline {
    agent any
    tools{
        terraform "1.7.1"
    }
    stages {
        stage('test') {

            steps {
                // Get some code from a GitHub repository
                sh " git clone 'https://github.com/permeenev/deploy_prod_instance.git'"
                sh "ls -la"
                sh "terraform --version"
            }

        }
    }
}
