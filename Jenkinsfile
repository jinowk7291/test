node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("jinowk7291/test")
         
     }
     stage('Push image') {
         docker.withRegistry('https://687227541429.dkr.ecr.ap-northeast-2.amazonaws.com', 'ecr:ap-northeast-2:bar-ecr-credentials') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}