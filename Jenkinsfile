pipeline {
  agent any
  stages {
    stage('Back test') {
      parallel {
        stage('DBunit') {
          steps {
            catchError()
          }
        }

        stage('Postman') {
          steps {
            error 'error al insertar'
          }
        }

      }
    }

    stage('Front test') {
      parallel {
        stage('Front test') {
          steps {
            warnError(message: 'error al mostrar')
          }
        }

        stage('Android') {
          steps {
            catchError()
          }
        }

        stage('iOS') {
          steps {
            catchError()
          }
        }

        stage('Chrome') {
          steps {
            catchError()
          }
        }

      }
    }

    stage('Develop') {
      steps {
        git(url: 'https://github.com/nfmorenog/ingesoft2', branch: 'development')
      }
    }

    stage('Deploy') {
      steps {
        git(url: 'https://github.com/nfmorenog/ingesoft2', branch: 'master')
      }
    }

  }
}