pipeline {
  agent any
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

        stage('chekout code') {
          steps {
            git(url: 'https://github.com/raeeceip/devops-django-react-task-2', branch: 'master')
          }
        }

      }
    }

    stage('list contents') {
      parallel {
        stage('list contents') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Frontend Unit Test') {
          steps {
            sh 'cd frontend && npm i && npm run test'
          }
        }

      }
    }

  }
}