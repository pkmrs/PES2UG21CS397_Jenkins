pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: 'https://github.com/pkmrs/PES2UG21CS397_Jenkins.git']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS397-1'
          sh 'g++ sample.cpp -o output'
        }
    }
    stage('Test'){
        steps {
            sh './output'
        }
    }
    stage('Deploy') {
        steps {
            echo 'deploy'
        }
    }
}
post{
  failure{
    error 'Pipeline failed'
  }
}
}
  
  
