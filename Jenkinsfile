pipeline{
    agent any
    stages{
        stage('Lint HTML'){
            steps{
                sh 'tidy -q -e *.html'
            }
        }
        stage("Upload-HTML-file-to-S3"){
            steps{
                withAWS(region:'us-west-2', credientals:'aws-static') {
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'pipeline-to-aws-s3')
                }
            }
        }
    }
}