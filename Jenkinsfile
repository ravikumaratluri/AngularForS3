pipeline{
  agent any
  stages{
    stage ('checkout'){
      steps{
        checkout scm
      }
    }
    stage ('Bucket Create'){
      steps{
        sh 'aws s3api create-bucket --bucket my-bucket-ravi-1234 --region us-east-1'
      }
    }
  }
}