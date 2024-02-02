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
                        sh """if ! [ -e 'vkcs_provider.tf' ] ; then
                                cp '$vkcs_provider' vkcs_provider.tf 
                            fi"""
                    }
                script {
                    properties([
                        parameters([
                            choice(
                                choices: [ 'plan', 'apply -auto-approve', 'destroy -auto-approve'], 
                                name: 'terraform_do' )
                                ])
                            ])
                    sh "ls -la"
                    sh "terraform --version"
                    sh "terraform init"
                    sh "terraform $terraform_do "
                }
            }

        }
    }
}
