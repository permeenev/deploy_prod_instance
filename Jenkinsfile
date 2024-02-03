pipeline {
    agent any
    tools{
        terraform "terraform1.7.2"
    }
    stages {
        stage('test') {
            steps {
                withCredentials([file(
                    credentialsId: '12755954-d6b3-46af-9a98-2bc94d8a2a42', 
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
                    sh "terraform init"
                    sh "terraform $terraform_do "
                }
            }

        }
    }
}
