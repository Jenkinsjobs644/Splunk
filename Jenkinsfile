pipeline {
  agent any
  stages {
    stage('Stage1') {
      parallel {
        stage('Stage1') {
          steps {
            echo 'This is stage1'
          }
        }
        stage('get file from S3') {
          steps {
            s3Download(file: 'splunkforwarder-7.1.2-a0c72a66db66-Linux-x86_64.tgz', bucket: 'helloworld.nonprod.pge.com')
          }
        }
      }
    }
    stage('Install Splunk Forwarder') {
      steps {
        build 'SplunkForwarderInstall'
      }
    }
  }
  environment {
    AWS_ACCESS_KEY_ID = ''
    AWS_SECRET_ACCESS_KEY = ''
    REGION = 'us-west-2'
  }
}