pipeline {
    agent any

    environment {
        BRANCH_NAME = "main"
        GIT_URL = "https://github.com/Abigaelmars/aws-cicd.git"
        IMAGE_TAG = "abigaelmars/aws-cicd"
        IMAGE_VERSION = "${BUILD_NUMBER}"
    }
stages {
    stage('git checkout'){
        steps{
            git branch: "${BRANCH_NAME}", url: "${GIT_URL}"
        }
    }
    stage( 'docker build'){
        steps{
            sh 'docker build -t "${IMAGE_TAG}:${BUILD_VERSION}" .'
            sh 'docker images'
        }
    }
}

}