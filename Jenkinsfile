node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("https://687227541429.dkr.ecr.ap-northeast-2.amazonaws.com/bar")
     }
     stage('Push image') {
         sh 'rm  ~/.dockercfg || true'
         sh 'rm ~/.docker/config.json || true'
          
         docker.withRegistry('https://687227541429.dkr.ecr.ap-northeast-2.amazonaws.com', 'ecr:ap-northeast-2:admin') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

