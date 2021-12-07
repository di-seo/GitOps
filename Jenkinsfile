pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://git.linecorp.com/di-seo/GitOps.git will replace by sed command before RUN
        git url: 'https://github.com/di-seo/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}
