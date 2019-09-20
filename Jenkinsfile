pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh '''# Build new image and push to ACR.
WEB_IMAGE_NAME="${ACR_LOGINSERVER}/azure-vote-front:kube${BUILD_NUMBER}"
docker build -t $WEB_IMAGE_NAME ./azure-vote
docker login ${ACR_LOGINSERVER} -u ${ACR_ID} -p ${ACR_PASSWORD}
docker push $WEB_IMAGE_NAME'''
      }
    }
  }
  environment {
    ACR_LOGIN = 'wuerzelchen'
    ACR_PASSWORD = '8UAF+WXrbOJpkbD1TZG573c23QOBkCw1'
    ACR_REGISTRY = 'wuerzelchen.azurecr.io'
  }
}