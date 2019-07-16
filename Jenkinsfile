pipeline {
    agent { label 'vm-int-jenkins-slave' }
    stages {
        stage ('deploy') {
          when { not { branch 'master' } }
          steps {
              sh 'mvn -B clean deploy'
          }
        }
        stage ('install') {
          when { branch 'master' }
          steps {
              sh 'mvn -B clean install'
          }
        }
    }
}