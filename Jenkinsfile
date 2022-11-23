pipeline {
  agent {
    docker {
      image 'frontend'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "Hello World"'
            sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
          }
        }

        stage('docker build') {
          agent {
            docker {
              image '/frontend'
            }

          }
          steps {
            sh 'cd frontend'
          }
        }

      }
    }

  }
}