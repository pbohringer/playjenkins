pipeline {

  agent { label 'jenkins-slave' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/pbohringer/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
