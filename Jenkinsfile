pipeline{
    agent any
    stages{
        stage('Upload HTML file to S3'){
            steps{
                withAWS(region:'us-west-2', credentials:'aws-static') {
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'pipeline-to-aws-s3')
                }
            }
        }
    }
}
