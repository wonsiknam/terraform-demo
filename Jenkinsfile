pipeline {
  agent any
  stages {
    stage('terraform-init') {
      steps {
        sh 'terraform init -input=false'
      }
    }
    stage('terraform-validate') {
      steps {
        sh 'terraform validate -json'
      }
    }
    stage('terraform-plan') {
      steps {
        sh 'terraform plan -input=false'
      }
    }
    stage('terraform-apply') {
      steps {
        input "Confirm & Apply"
        sh 'terraform apply -input=false -auto-approve'
      }
    }
  }
