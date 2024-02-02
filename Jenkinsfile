pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                // Get some code from a GitHub repository
                sh " 
                git clone 'https://github.com/permeenev/deploy_prod_instance.git'
                "
                sh "
                wget https://hashicorp-releases.mcs.mail.ru/terraform/1.7.1/terraform_1.7.1_linux_amd64.zip
                "
                sh "
                unzip terraform_1.7.1_linux_amd64.zip
                "
                sh "
                ls -la
                "
                sh "
                terraform --version
                "
            }

        }
    }
}
