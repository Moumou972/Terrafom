properties([pipelineTriggers([githubPush()])])
pipeline {
    agent {
	 docker{
            image 'hashicorp/terraform'
            args  '--entrypoint='
         }
     }
    stages {
        stage('init terraform') {
            steps {
               sh 'terraform init'
            }
        }
        stage('Plan terraform code'){
            steps {
              sh 'terraform plan'
            }
        }
        stage('Apply terraform code'){
            steps {
              sh 'terraform apply -auto-approve'
            }
        }
    }
}
