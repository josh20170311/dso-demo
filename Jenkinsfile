pipeline {
  agent {
    kubernetes {
      yamlFile 'build-agent.yaml'
      defaultContainer 'maven'
      idleMinutes 1
    }

  }
  stages {
    stage('kaniko') {
      steps {
        container('kaniko'){
                    sh 'echo "from hello-world" >> Dockerfile'
                    sh 'echo "Entrypoint ["/hello"]" >> Dockerfile'
                    sh 'find / | grep .docker'
                    sh 'ls / -al'
                    sh 'ls /kaniko -al'
                    sh 'cat /kaniko/.docker/config.json'
                    sh 'ls /kaniko/.docker -al'
                    sh 'cat /kaniko/.docker/*'
                    sh '/kaniko/executor -f Dockerfile -d josh951753/hello --skip-tls-verify'
                    
        }
      }
    }
  }
}
