pipeline{
 agent {
        docker {
            image 'hashicorp/terraform:latest'
            // Override the ENTRYPOINT
            args '--entrypoint=""'
        }
    }

  stages{
    stage('init'){
      steps{
        sh 'terraform init -upgrade -no-color'
      }
    }

    stage('validate'){
      steps{
        sh 'terraform validate -no-color'
      }
    }

    stage('plan'){
      steps{
        sh 'terraform plan -no-color'
      }
    }

    // stage('apply'){
    //   steps{
    //     sh 'terraform apply --auto-approve -no-color'
    //   }
    // }

     stage('destroy'){
      steps{
        sh 'terraform destroy --auto-approve -no-color'
      }
    }
  }
  
}
  