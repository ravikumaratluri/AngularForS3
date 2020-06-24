pipeline{
  agent any
  stages{

    stage ('checkout'){
      steps{
        checkout scm
      }
    
    }
    stage ('Angular cli'){
      steps{
         bat 'npm install'
         bat 'npm install -g @angular/cli@8'
         bat 'ng build'
      }
    }

    stage ('Bucket Create'){
      steps{
        sh 'aws s3api create-bucket --bucket my-bucket-ravi-1234 --region us-east-1'
      }
    }

    stage ('Copy to bucket'){
      steps{
        sh 'aws s3 cp dist/ s3://my-bucket-ravi-1234/ --recursive --region us-east-1'
      }
    }

  }
}