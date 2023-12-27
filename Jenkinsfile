pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        AWS_ELASTIC_BEANSTALK_APPLICATION_NAME = 'practice'
        AWS_ELASTIC_BEANSTALK_ENVIRONMENT_NAME = 'Practice-env'
        AWS_S3_BUCKET = 'yashbucketdhhffh'
    }

    stages {
        stage('Build') {
            steps {
                // Your build steps here
            }
        }

        stage('Deploy to Elastic Beanstalk') {
            steps {
                script {
                    // Deploy to Elastic Beanstalk using EB CLI
                    withAWS(region: AWS_DEFAULT_REGION, role: 'arn:aws:iam::741409500357:role/jenkins-practice-role') {
                        sh "eb deploy $AWS_ELASTIC_BEANSTALK_ENVIRONMENT_NAME \
                            --region $AWS_DEFAULT_REGION \
                            --verbose"
                    }
                }
            }
        }
    }
}
