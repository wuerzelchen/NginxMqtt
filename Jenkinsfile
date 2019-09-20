pipeline {
  agent any
  stages {
    stage('Build and Push') {
      steps {
        sh '''# Build new image and push to ACR.
WEB_IMAGE_NAME="${ACR_LOGINSERVER}/azure-vote-front:kube${BUILD_NUMBER}"
docker build -t $WEB_IMAGE_NAME ./azure-vote
docker login ${ACR_LOGINSERVER} -u ${ACR_NAME} -p ${ACR_PASSWORD}
docker push $WEB_IMAGE_NAME'''
      }
    }
  }
  environment {
    ACR_NAME = 'wuerzelchen'
    ACR_PASSWORD = '8UAF+WXrbOJpkbD1TZG573c23QOBkCw1'
    ACR_LOGINSERVER = 'wuerzelchen.azurecr.io'
  }
}