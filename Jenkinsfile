pipeline {
  agent any
  stages {
    stage('error') {
      parallel {
        stage('error') {
          steps {
            s3Download(file: 'splunkforwarder-7.1.2-a0c72a66db66-Linux-x86_64.tgz', bucket: 'helloworld.nonprod.pge.com')
          }
        }
        stage('') {
          steps {
            awsIdentity()
          }
        }
      }
    }
  }
}