// pipeline {
//   agent any
//   stages {
//     stage('Build') {
//       steps {
//         sh 'docker-compose build'
//       }
//     }
//     stage('Test') {
//       steps {
//         sh 'npm test'
//       }
//     }
//     stage('Deploy') {
//       steps {
//         sh 'docker-compose up -d'
//       }
//     }
//   }
// }




pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker-compose build'
      }
    }
    stage('Test') {
      steps {
        script {
          docker.image('node:16').inside {
            sh 'npm install'
            sh 'npm test'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker-compose up -d'
      }
    }
  }
}