pipeline {
    agent any
    tools{
        terraform "terraform1.7.1"
    }
    stages {
        stage('test') {
            steps {
                withCredentials([file(
                    credentialsId: 'd2cfaab2-c8e8-49fa-bb7e-ee8542e19d69', 
                    variable: 'vkcs_provider')]){
                        sh "cp '$vkcs_provider' vkcs_provider.tf"
                    }
                script {
                    sh "ls -la"
                    sh "terraform --version"
                    sh "terraform init"
                    sh "terraform apply -auto-approve"
                    sh 'terraform state list'
                }
            }

        }
    }
}
