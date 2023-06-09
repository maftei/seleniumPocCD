pipeline {
  agent any
      environment{
          PATH = "/opt/maven/apache-maven-3.8.6/bin:$PATH"

      }

    stages {

      stage ('Checkout SCM'){
        steps {
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/maftei/seleniumPocCD.git']]])
        }
      }

      stage('Create docker container') {
                      steps {
                          sh 'docker run -d  -e HUB_HOST=44.203.64.191  -e MODULE=search-module.xml selenium-docker-epay'
                      }
                  }
   }
}