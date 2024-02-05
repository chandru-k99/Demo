pipeline {
  agent any
    stages {
      stage ('One') {
        steps {
          echo "Hi,Stage1"
        }
      }
      stage ('two') {
        steps {
          input ('do you want to proceed?')
        }
      }
      stage ('Three') {
        when {
          not {
            branch "master"
          }
        }
        steps{
          echo "Hello after when block"
        }
      }
      stage ('Four') {
        parallel {
          stage ('unit testing') {
            steps (
              echo "running unit test"
              }
          }
          stage ('Integeration test') {
            agent {
              docker {
                resueNode false
                image 'ubuntu'
              }
            }
            steps {
              echo 'running it on docker container'
            }
          }
              }
              }              
    }
}
